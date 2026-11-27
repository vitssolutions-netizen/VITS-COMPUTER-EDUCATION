name: Auto Fill Computer Training Application

on:
  push:
    paths:
      - 'input_pdfs/**.pdf'

permissions:
  contents: write

jobs:
  autofill:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v5
        with:
          python-version: '3.11'

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Run autofill script
        run: python autofill.py

      - name: Commit and push filled PDFs
        run: |
          git config --local user.email "action@github.com"
          git config --local user.name "GitHub Action"
          git add output_forms/
          git diff --staged --quiet || git commit -m "Auto-filled application form"
          git push
