# PPCYI_T1_VJ_1492_25_1685
DOCUMETNOS DEL CURSO DE PROGRAMACION II

VIDEO DE YOUTUBE LINK DE VISUALIZACION
https://youtu.be/qsfAcONc4mE


DIAGRAMA DE CLASES


%% =====================
%% Modelo de dominio
%% =====================
class Vuelo {
  +codigo: str
  +origen: str
  +destino: str
  +duracion: int
  +aerolinea: str
  +__str__() str
}

%% =====================
%% Módulo: Acceso / Parsing XML
%% =====================
class AccesoXML <<module>> {
  +cargar_archivo(ruta: str) List~Vuelo~
  -_texto_obligatorio(nodo: Element, etiqueta: str) str
}

%% =====================
%% Módulo: Servicios (lógica de negocio)
%% =====================
class Servicios <<module>> {
  +buscar_vuelo_por_codigo(vuelos: List~Vuelo~, codigo: str) Optional~Vuelo~
  +agrupar_por_aerolinea(vuelos: List~Vuelo~) Dict~str, List~Vuelo~~
  +ordenar_por_duracion_desc(vuelos: List~Vuelo~) List~Vuelo~
}

%% =====================
%% Módulo: Presentación (consola)
%% =====================
class Consola <<module>> {
  +limpiar_consola() None
  +pausar() None
  +mostrar_menu() None
  +main() None
}

%% =====================
%% Dependencias entre módulos
%% =====================
AccesoXML ..> Vuelo : crea/retorna
Servicios ..> Vuelo : usa
Consola ..> AccesoXML : invoca
Consola ..> Servicios : invoca
```
