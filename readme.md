# Document (PDF) Optical Characeter Recognition

Converts .pdf files to .docx and .tex formats using the GOT-OCR2_0 model for text extraction and formatting.

## Features

- Converts .pdf files to .docx format
- Converts the resulting .docx file to .tex format
- Uses state-of-the-art OCR technology (GOT-OCR2_0 model) for accurate text extraction
- Maintains formatting, including page breaks and LaTeX-specific elements

## Requirements

- CUDA-compatible GPU (for the GOT-OCR2_0 model)

### Required Python packages:

- python-docx
- transformers
- PyMuPDF
- Pillow
- accelerate
- tiktoken
- verovio

You can install the required packages using pip:

```sh
pip install -r requirements.txt
```

## Usage

To use the script, run it from the command line with the following syntax:

```
python script.py --pdf_name <input_pdf> [--doc_name <output_docx>] [--tex_name <output_tex>]
```

### Arguments:

- `--pdf_name`: (Required) Name of the input PDF file
- `--doc_name`: (Optional) Name of the output DOCX file (default: doc_output.docx)
- `--tex_name`: (Optional) Name of the output TEX file (default: tex_output.tex)

### Example:

```
python script.py --pdf_name input.pdf --doc_name output.docx --tex_name output.tex
```

This command will convert `input.pdf` to `output.docx` and then to `output.tex`.

## How it works

1. The script loads the GOT-OCR2_0 model and tokenizer.
2. It converts each page of the PDF to an image.
3. The GOT-OCR2_0 model performs OCR on each image, extracting the text.
4. The extracted text is compiled into a DOCX file.
5. The DOCX file is then converted to a LaTeX (TEX) file, maintaining formatting.

## Notes

- The script requires a CUDA-compatible GPU for optimal performance.
- Large PDF files may take some time to process (~9 seconds/page)
- The quality of the OCR results depends on the clarity and quality of the input PDF.


## Contact
For any queries, please reach out at sadmansakib26@iut-dhaka.edu.