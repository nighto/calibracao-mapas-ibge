calibracao-mapas-ibge
=====================

Coleção de arquivos de calibração do PicLayer/JOSM (.cal) para os mapas do IBGE

O que são arquivos .cal
-----------------------

Os arquivos .cal são arquivos de calibração gerados pelo plugin [PicLayer](http://wiki.openstreetmap.org/wiki/JOSM/Plugins/PicLayer) do [JOSM](http://josm.openstreetmap.de/), um editor de mapas do [OpenStreetMap](http://openstreetmap.org/).

A que se referem estes arquivos .cal
------------------------------------

Os arquivos de calibração deste repositório são referentes aos arquivos do servidor [GeoFTP](ftp://geoftp.ibge.gov.br) do [IBGE](http://ibge.gov.br), mais especificamente aos arquivos PDF. Os dados do IBGE são de domínio público, porém devem sempre serem importados para o OSM com a tag `source=IBGE`.

Como usar os arquivos de calibração deste repositório
-----------------------------------------------------

Os arquivos PDF não podem ser utilizados diretamente pelo PicLayer, devendo primeiro serem convertidos para jpeg ou png. **Usamos por padrão a densidade de 300.**

    convert -density 300 mapa.pdf mapa.jpg

O argumento `-density 300` garante que as letras do mapa do IBGE continuem visíveis no JOSM. Se o mapa em pdf tiver mais de uma página ele geralmente cria os arquivos assim: mapa-0.jpg, mapa-1.jpg etc. O convert é um pacote do [ImageMagick](http://www.imagemagick.org/).

No JOSM, posicione as coordenadas mais ou menos na região de onde seria o mapa, selecione a aba PicLayer e carrege o mapa.jpg.

Agora vem a parte mais chatinha que é calibrar o mapa. Como os mapas do IBGE vem com as latitudes/longitudes dá para marcar os pontos e arrastá-los. Requer um pouquinho de prática, mas uma vez que está feito ele salva a calibração num arquivo mapa.jpg.cal e fica pronto. No site do PicLayer tem um tutorial de como isto é feito (http://wiki.openstreetmap.org/wiki/JOSM/Plugins/PicLayer).

Suba os arquivos neste repositório seguindo o mesmo nome e a mesma estrutura de pastas do ftp original. Por exemplo, o arquivo `ftp://geoftp.ibge.gov.br/mapas_estatisticos/censo_2007/mapa_municipal_estatistico/df/brasilia.pdf` deve estar no repositório como `mapas_estatisticos/censo_2007/mapa_municipal_estatistico/df/brasilia.jpg.cal`.