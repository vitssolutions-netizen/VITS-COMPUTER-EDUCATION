<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>VITS Computer Education - Official Application Form</title>
<style>
  body {
    background-color: #e9ecef;
    font-family: "Times New Roman", Times, serif;
    font-size: 12pt;
    line-height: 1.4;
    margin: 0;
    padding: 20px;
    color: #000;
  }

  /* A4 Sheet Exact Dimensions */
  .a4-page {
    width: 210mm;
    min-height: 297mm;
    padding: 15mm 18mm;
    margin: auto;
    background: #fff;
    box-shadow: 0 0 12px rgba(0, 0, 0, 0.2);
    box-sizing: border-box;
    position: relative;
  }

  /* Header Section */
  .header {
    text-align: center;
    border-bottom: 2px solid #000;
    padding-bottom: 8px;
    margin-bottom: 14px;
  }

  .header h1 {
    font-family: "Times New Roman", Times, serif;
    font-size: 20pt;
    font-weight: bold;
    margin: 0;
    letter-spacing: 1px;
    text-transform: uppercase;
  }

  .header .tagline {
    font-size: 11pt;
    margin: 2px 0 6px 0;
  }

  .form-title {
    display: inline-block;
    border: 1.5px solid #000;
    padding: 3px 18px;
    font-weight: bold;
    font-size: 12pt;
    text-transform: uppercase;
    margin-top: 4px;
  }

  /* Meta Bar (Application No & Date) */
  .meta-bar {
    display: flex;
    justify-content: space-between;
    margin-bottom: 12px;
    font-weight: bold;
  }

  /* Top Section: Personal Details + Photo Box */
  .top-section {
    display: flex;
    justify-content: space-between;
    gap: 15px;
    margin-bottom: 14px;
  }

  .personal-table {
    width: 100%;
    border-collapse: collapse;
  }

  .photo-box {
    width: 35mm;
    height: 45mm;
    border: 1.5px solid #000;
    flex-shrink: 0;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    font-size: 10pt;
    padding: 4px;
    box-sizing: border-box;
  }

  /* General Table Styling */
  table {
    width: 100%;
    border-collapse: collapse;
    margin-bottom: 14px;
    font-size: 12pt;
  }

  th, td {
    border: 1px solid #000;
    padding: 6px 8px;
    vertical-align: top;
    text-align: left;
  }

  th {
    background-color: #f4f4f4;
    font-weight: bold;
    text-align: center;
  }

  .section-heading {
    font-weight: bold;
    text-transform: uppercase;
    background-color: #eaeaea;
    padding: 4px 8px;
    border: 1px solid #000;
    border-bottom: none;
    font-size: 12pt;
  }

  .label {
    font-weight: bold;
    width: 34%;
  }

  /* Declaration & Signatures */
  .declaration {
    margin-top: 14px;
    text-align: justify;
    font-size: 12pt;
  }

  .signatures {
    display: flex;
    justify-content: space-between;
    margin-top: 45px;
    font-weight: bold;
  }

  .sig-block {
    text-align: center;
    width: 200px;
    border-top: 1px solid #000;
    padding-top: 5px;
  }

  /* Print Button & Media Query */
  .controls {
    text-align: center;
    margin-bottom: 15px;
  }

  .controls button {
    font-family: "Times New Roman", Times, serif;
    font-size: 12pt;
    font-weight: bold;
    padding: 8px 20px;
    cursor: pointer;
    background: #1a1a1a;
    color: #fff;
    border: none;
    border-radius: 4px;
  }

  @page {
    size: A4;
    margin: 0;
  }

  @media print {
    body {
      background: none;
      padding: 0;
    }
    .a4-page {
      box-shadow: none;
      margin: 0;
      width: 210mm;
      height: 297mm;
    }
    .controls {
      display: none;
    }
    th, .section-heading {
      -webkit-print-color-adjust: exact;
      print-color-adjust: exact;
    }
  }
</style>
</head>
<body>

  <div class="controls">
    <button onclick="window.print()">Print A4 Application</button>
  </div>

  <div class="a4-page">
    <!-- Institution Header -->
    <div class="header">
      <h1>VITS COMPUTER EDUCATION</h1>
      <div class="tagline">An ISO Certified Computer Training Institute | Excellence in IT Education</div>
      <div class="form-title">Application Form</div>
    </div>

    <!-- Application Number & Date -->
    <div class="meta-bar">
      <div>Application No: <span id="appNo">VITS-2026-001</span></div>
      <div>Date: <span id="appDate">27/11/2026</span></div>
    </div>

    <!-- Personal Details + Photo -->
    <div class="section-heading">1. Personal Details</div>
    <div class="top-section">
      <table class="personal-table" style="margin-bottom: 0;">
        <tr>
          <td class="label">Full Name</td>
          <td id="fullName">[AI Extracted Full Name]</td>
        </tr>
        <tr>
          <td class="label">Father's / Guardian's Name</td>
          <td id="fatherName">[AI Extracted Father's Name]</td>
        </tr>
        <tr>
          <td class="label">Date of Birth</td>
          <td id="dob">[DD/MM/YYYY]</td>
        </tr>
        <tr>
          <td class="label">Gender & Category</td>
          <td id="genderCategory">[Gender / Category]</td>
        </tr>
        <tr>
          <td class="label">Mobile Number</td>
          <td id="mobile">[+91 XXXXXXXXXX]</td>
        </tr>
        <tr>
          <td class="label">Email ID</td>
          <td id="email">[applicant@example.com]</td>
        </tr>
      </table>

      <div class="photo-box">
        Affix Recent<br>Passport Size<br>Photograph
      </div>
    </div>

    <!-- Address & Course Details -->
    <table>
      <tr>
        <td class="label" style="width: 28%;">Permanent Address</td>
        <td id="address">[AI Extracted Complete Residential Address]</td>
      </tr>
      <tr>
        <td class="label">Course Applied For</td>
        <td id="course"><strong>[AI Extracted Course Name]</strong></td>
      </tr>
      <tr>
        <td class="label">Preferred Batch Timing</td>
        <td id="batch">[Morning / Afternoon / Evening]</td>
      </tr>
    </table>

    <!-- Educational Qualifications -->
    <div class="section-heading">2. Educational Qualifications</div>
    <table>
      <thead>
        <tr>
          <th style="width: 22%;">Examination</th>
          <th style="width: 38%;">Board / University</th>
          <th style="width: 20%;">Year of Passing</th>
          <th style="width: 20%;">Percentage / CGPA</th>
        </tr>
      </thead>
      <tbody id="educationRows">
        <tr>
          <td>SSC / 10th</td>
          <td>[Board Name]</td>
          <td style="text-align: center;">[Year]</td>
          <td style="text-align: center;">[%]</td>
        </tr>
        <tr>
          <td>Intermediate / 12th</td>
          <td>[Board Name]</td>
          <td style="text-align: center;">[Year]</td>
          <td style="text-align: center;">[%]</td>
        </tr>
        <tr>
          <td>Degree / Diploma</td>
          <td>[University Name]</td>
          <td style="text-align: center;">[Year]</td>
          <td style="text-align: center;">[%]</td>
        </tr>
      </tbody>
    </table>

    <!-- Declaration -->
    <div class="declaration">
      <strong>Declaration:</strong> I hereby declare that all the statements and information furnished above are true, complete, and correct to the best of my knowledge and belief. I agree to abide by the rules and regulations of <strong>VITS COMPUTER EDUCATION</strong>.
    </div>

    <!-- Signatures -->
    <div class="signatures">
      <div class="sig-block">Signature of the Applicant</div>
      <div class="sig-block">Authorized Signatory<br><span style="font-size: 10pt; font-weight: normal;">(VITS Computer Education)</span></div>
    </div>
  </div>

</body>
</html>
