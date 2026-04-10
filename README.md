# Processo para renderizar os gráficos

pdflatex --shell-escape graficos/glenfiddich12.tex
convert -density 300 graficos/glenfiddich12.pdf graficos/glenfiddich12.png
