# tesseract4win64
charlesw/tesseract 4.0 build for x64 Windows.

This is a Win64 build of tesseract 4.0.0 beta, leptonica 1.75.3, and charlesw/tesseract .Net wrapper.

Tesseract 4.0.0 was built with OpenMP as follows.

cd \petri

mkdir Win64

cd Win64

git clone https://github.com/tesseract-ocr/tesseract tesseract

cd tesseract

cppan  (I assume this wasn't necessary, but I'm trying to avoid improvising)

mkdir Win64 && cd Win64

cppan ..

cmake .. -G "Visual Studio 15 2017 Win64"


Edit cppan.yml and uncomment, and edit, this line:

#generator: Visual Studio 14 2015 Win64 -> generator: Visual Studio 15 2017 Win64

cppan --generate .


Open the tesseract.sln created in this same folder using Visual Studio 2017, select the Release configuration.
Set OpenMP property and then build.
