cat("#########################################################\n");
cat(".Rprofile file is loading...\n");

requireNamespace('pkgbuild')

# Needed for rmarkdown which uses pdflatex.exe.
Sys.setenv(PATH = paste(Sys.getenv("PATH"), "W:\\Tools\\miktex\\program\\miktex\\bin", sep=.Platform$path.sep));
cat(paste("LaTeX installed:", pkgbuild::has_latex(), "\n"))

# RTools
Sys.setenv(PATH = paste(normalizePath("W:/Tools/rtools/program/mingw_64/bin", winslash = "/"),
                        Sys.getenv("PATH"), sep=.Platform$path.sep))
Sys.setenv(PATH = paste(normalizePath("W:/Tools/rtools/program/bin", winslash = "/"),
                        Sys.getenv("PATH"), sep=.Platform$path.sep))
# As of R 3.3 you need to set the path to the compiler using the BINPREF
# variable. This is because we ship two separate versions of gcc, one
# targeting win32 and one targeting win64. If you compile R packages you need both at
# the same time. Hence the "$(WIN)" variable in the BINPREF.
Sys.setenv(BINPREF = normalizePath("W:/Tools/rtools/program/mingw_64/bin/", winslash = "/"))
cat(paste("RTools installed:", pkgbuild::has_build_tools(debug = TRUE), "\n"))

# QPDF, used by CRAN to compress pdf's
Sys.setenv(PATH = paste(Sys.getenv("PATH"), "W:\\Tools\\pdf\\qpdf\\program\\x64\\bin", sep=.Platform$path.sep))

# Encoding for input/output. Set to UTF-8 and also make sure that IDE (RStudio) saves files in UTF-8.
# Default is "native.enc" and knitr, while reading files, might miss that they are in UTF-8.
# Also, for project cross-platform compatibiity, I think UTF-8 is better than native.
options(encoding = "UTF-8")

# Might be dangerous in some cases, but improves portability of code.
# Sys.timezone(): default is usualy "Europe/Paris" or similar.
Sys.setenv(TZ = "UTC")

cat(".Rprofile file loaded for project.\n")
cat("#########################################################\n")
