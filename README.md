import os
import re
from pypdf import PdfReader
from reportlab.lib.pagesizes import A4
from reportlab.pdfgen import canvas

INPUT_DIR = "input_pdfs"
OUTPUT_DIR = "output_forms"

os.makedirs(INPUT_DIR, exist_ok=True)
os.makedirs(OUTPUT_DIR, exist_ok=True)

def extract_details_from_pdf(pdf_path):
    reader = PdfReader(pdf_path)
    full_text = ""
    for page in reader.pages:
        full_text += (page.extract_text() or "") + "\n"

    # సాధారణ పాటర్న్స్ ద్వారా వివరాలు తీయడం (మీ PDF ఫార్మాట్ బట్టి వీటిని మార్చుకోవచ్చు)
    name_match = re.search(r"(?:Name|Full Name)\s*[:\-]\s*(.+)", full_text, re.IGNORECASE)
    phone_match = re.search(r"(?:Phone|Mobile|Contact)\s*[:\-]\s*([+\d\s\-]{8,15})", full_text, re.IGNORECASE)
    email_match = re.search(r"[\w\.-]+@[\w\.-]+\.\w+", full_text)
    course_match = re.search(r"(?:Course|Program)\s*[:\-]\s*(.+)", full_text, re.IGNORECASE)
    qual_match = re.search(r"(?:Qualification|Education)\s*[:\-]\s*(.+)", full_text, re.IGNORECASE)

    return {
        "name": name_match.group(1).strip() if name_match else "Not Found",
        "phone": phone_match.group(1).strip() if phone_match else "Not Found",
        "email": email_match.group(0).strip() if email_match else "Not Found",
        "course": course_match.group(1).strip() if course_match else "Basic Computers",
        "qualification": qual_match.group(1).strip() if qual_match else "Not Specified",
    }

def generate_filled_form(data, output_path):
    c = canvas.Canvas(output_path, pagesize=A4)
    width, height = A4

    c.setFont("Times-Bold", 15)
    c.drawCentredString(width / 2, height - 50, "APPLICATION FOR COMPUTER TRAINING PROGRAM")

    c.setFont("Times-Roman", 11)
    y = height - 100
    rows = [
        ("Full Name", data["name"]),
        ("Mobile Number", data["phone"]),
        ("Email ID", data["email"]),
        ("Qualification", data["qualification"]),
        ("Course Applied For", data["course"]),
    ]

    for label, value in rows:
        c.setFont("Times-Bold", 11)
        c.drawString(60, y, f"{label}:")
        c.setFont("Times-Roman", 11)
        c.drawString(220, y, str(value))
        c.line(215, y - 3, width - 60, y - 3)
        y -= 30

    c.save()

def main():
    for filename in os.listdir(INPUT_DIR):
        if filename.lower().endswith(".pdf"):
            in_path = os.path.join(INPUT_DIR, filename)
            out_path = os.path.join(OUTPUT_DIR, f"FILLED_{filename}")
            data = extract_details_from_pdf(in_path)
            generate_filled_form(data, out_path)
            print(f"Processed {filename} -> {out_path}")

if __name__ == "__main__":
    main()
