FROM ruby:3-alpine@sha256:df559e1eb3c1b4884a28caa43ce163425a7f81cf9b7372d33883cf0fea67303f
# los tres comandos RUN en la misma linea para optimizar espacio en la imagen
RUN apk add --update build-base && gem install sinatra && gem install thin
# ADD solo para archivos comprimidos (copia + descomprime), usar COPY para el resto (solo copia)
COPY hasher.rb /
# CMD  ["ruby", "hasher.rb"]  --> Lo sustituimos por entrypoint + cmd
ENTRYPOINT ["ruby"]
CMD ["hasher.rb"]
EXPOSE 8080
