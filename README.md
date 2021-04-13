# Glyph-Recognition
Glyph recognition from an input

## Main idea :
1. Store glyphes as black and alpha on fixed size square canvas pngs in a data bank
2. After drawn input, produce black and alpha binary png from input, image bounds are defined by min / max x, y colored pixel within the input
3. Rescale to a square canvas by identifying which of the bound axys is greater, and scale this png image axys to match the lowest
4. Scale to the fixed size of glyph from data bank
5. For each existing glyphs compare by filter substracting input to glyphe and weight result from quantity of black pixels remaining, if weight is below threshold and lower than actual stored candidate, replace candidate by the actual one in the loop
6. If result : return glyphe id, if empty : false

## Optimisation possibility :
1. Manualy assign flags to glyphs data bank (Edged, Curved, Closed, Open, Composed, ...)
2. While input is made identify present flags within input
3. Before step `5.` of `Main idea` filter the glyphs set from querying only those which have the exact matching flags from input
