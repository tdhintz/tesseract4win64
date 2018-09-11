# tesseract4win64
charlesw/tesseract 4.0 build for x64 and x86 Windows.

This is a build of tesseract 4.0.0 beta, leptonica 1.77.0, and charlesw/tesseract .Net wrapper from September 10th sources.

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

Custom Leptonic settings include:
1. NO_CONSOLE_IO added to Preprocessor definitions.
2. Enable intrinsic functions: Yes.
3. Floating point model: Fast.
4. Enable COMDAT folding: Yes.
5. Use link time code generation: Yes.

Custom Tesseract 4.0 settings include:
1. Floating point model: Fast.
