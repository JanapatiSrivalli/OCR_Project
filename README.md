# OCR_Project
import cv2
import pytesseract

# Path to Tesseract executable (update this with your installation path)
pytesseract.pytesseract.tesseract_cmd = r'C:\Users\janapatis\Gitfolder\virtual_env\tesseract.exe'

def ocr_image(image_path, output_file):
    # Load the image
    image = cv2.imread(image_path)

    # Convert to grayscale
    gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

    # Perform OCR
    text = pytesseract.image_to_string(gray_image)

    # Write the extracted text to the output file
    with open(output_file, "w") as f:
        f.write(text)

if __name__ == "__main__":
    image_path = r"C:\Users\janapatis\Gitfolder\virtual_env\surya-master\dreamteam.jpg"  # Update with your image file
    output_file = "output.txt"  # Specify the output file name
    ocr_image(image_path, output_file)
    print(f"Extracted text saved to {output_file}")
