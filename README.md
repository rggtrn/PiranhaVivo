
# PirañaVivo

PirañaVivo es una aplicación basada en OpenFrameworks para mezclar videos que utilizan el códec Hap en vivo. PV se controla por medio del protocolo OSC y persigue la ligereza y la eficiencia como premisa. Está basado en [CineVivo](https://github.com/essteban/CineVivo). Para ejecutarlo es necesario utilizar un programa o dispositivo externo que pueda enviar mensajes OSC. 

## Instalación

PirañaVivo corre en Linux y Mac. En primer instancia, es necesario tener una versión compilada de OpenFrameworks. Para compilar PV es necesario agregar ofxSyphon (sólamente para mac) y una rama específica de la extensión ofxHapPlayer:

$ git clone https://github.com/astellato/ofxSyphon

$ git clone https://github.com/bangnoise/ofxHapPlayer
$ cd addons/ofxHapPlayer
$ git checkout OpenFrameworks-0.9

Una vez realizado esto, es posible compilar con Xcode o make, dependiendo de la arquitectura. Para compilar en Linux es necesario eliminar la línea ofxSyphon del archivo addons.make.

## Uso

PV utiliza el códec Hap, con lo cual es posible utilizar de forma eficiente videos con y sin opacidad.

### Videos en Hap

La conversión de videos es posible con ffmpeg. En macOS es posible instalar FFmpeg con soporte para hap con [brew](https://brew.sh/index_es):

brew install ffmpeg --with-snappy

* Para convertir videos en Hap

ffmpeg -i yourSourceFile.mov -c:v hap outputName.mov

* Para convertir videos en Hap Aplha

ffmpeg -i yourSourceFile.mov -c:v hap -format hap_alpha outputName.mov

* Para instrucciones más detalladas en inglés: https://gist.github.com/dlublin/e4585b872dd136ae88b2aa51a6a89aac

### Mensajes OSC

Próximamente. 