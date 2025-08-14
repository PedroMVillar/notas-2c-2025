# ------------------------------ Config ------------------------------
MAIN    = Ing2025
SRC_DIR = .
OUT_DIR = ..

LATEX = lualatex -interaction=nonstopmode

# ------------------------------ Reglas ------------------------------
all: $(OUT_DIR)/$(MAIN).pdf

inputs_auto.tex: $(wildcard clases/*.tex)
	@echo.> inputs_auto.tex
	@for %%f in (clases\*.tex) do @echo \input{clases/%%~nxf}>> inputs_auto.tex

$(OUT_DIR)/$(MAIN).pdf: $(SRC_DIR)/$(MAIN).tex inputs_auto.tex
	$(LATEX) -output-directory=$(SRC_DIR) $(SRC_DIR)/$(MAIN).tex
	$(LATEX) -output-directory=$(SRC_DIR) $(SRC_DIR)/$(MAIN).tex
	@if exist $(MAIN).pdf move /Y $(MAIN).pdf $(OUT_DIR) >nul

clean:
	-del /Q $(SRC_DIR)\*.aux $(SRC_DIR)\*.log $(SRC_DIR)\*.out $(SRC_DIR)\*.toc $(SRC_DIR)\*.synctex.gz $(SRC_DIR)\inputs_auto.tex 2>nul

.PHONY: all clean
