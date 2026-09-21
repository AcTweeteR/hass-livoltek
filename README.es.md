# Home Assistant Livoltek

Integración personalizada para monitorizar instalaciones Livoltek desde Home Assistant mediante el portal cloud de Livoltek.

> Es una integración HACS, no una App/add-on de Home Assistant.

## Instalación con HACS

[![Abrir en HACS](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=AcTweeteR&repository=hass-livoltek&category=integration)

Si el botón no funciona o Livoltek todavía no aparece en el catálogo general:

1. Abre **HACS → Integraciones**.
2. Pulsa **⋮ → Repositorios personalizados**.
3. Añade:

```text
https://github.com/AcTweeteR/hass-livoltek
```

4. Selecciona **Integración**.
5. Busca **Livoltek** en HACS y pulsa **Descargar**.
6. Reinicia Home Assistant si HACS lo solicita.
7. Ve a **Ajustes → Dispositivos y servicios → Añadir integración**.
8. Busca **Livoltek** y completa la configuración.

**Importante:** instalarla desde HACS y añadirla desde Dispositivos y servicios son dos pasos diferentes.

## Configuración

No es necesario modificar `configuration.yaml`.

La integración solicita los datos que necesita el cliente cloud de Livoltek:

- API key;
- `secuid`;
- user token;
- servidor/región cuando corresponda;
- instalación o Site que se desea monitorizar.

Estos valores son sensibles. No los publiques en incidencias, capturas, logs ni diagnósticos sin revisar.

## Sensores

Según los datos disponibles en el portal, la integración puede crear sensores de:

- estado de carga de la batería;
- potencia instantánea de red;
- producción solar;
- consumo de la vivienda/carga;
- potencia de batería;
- energía importada de red durante el día;
- energía exportada durante el día;
- producción solar diaria.

Los sensores diarios de energía están preparados como `total_increasing` cuando corresponde para facilitar su uso con el panel Energía de Home Assistant.

La disponibilidad exacta depende de lo que el portal Livoltek devuelva para tu instalación.

## Funcionamiento

La integración es de solo lectura y consulta el cloud de Livoltek periódicamente. No abre puertos ni instala un servicio local y no envía órdenes de control al inversor.

Si el inversor o el portal deja temporalmente de devolver mediciones, la integración intenta conservar el último dato válido cuando es posible. También incluye recuperación ante determinados casos de sesión/token caducado.

## Actualizaciones

HACS muestra las nuevas releases disponibles mediante el sistema habitual de actualizaciones de Home Assistant.

Antes de actualizar consulta [CHANGELOG.md](CHANGELOG.md). Si HACS solicita reiniciar Home Assistant después de instalar una versión nueva, hazlo.

## Problemas frecuentes

Si deja de actualizar:

1. Comprueba que Home Assistant tiene Internet.
2. Verifica que los datos del portal Livoltek continúan siendo válidos.
3. Abre **Ajustes → Dispositivos y servicios → Livoltek**.
4. Revisa los registros buscando `custom_components.livoltek` o `pylivoltek`.
5. Descarga diagnósticos si vas a abrir una incidencia.

Nunca publiques API keys, tokens, contraseñas ni el `secuid` completo.

## Documentación

- [Instalación](docs/installation.md)
- [Configuración](docs/configuration.md)
- [Sensores](docs/sensors.md)
- [Solución de problemas](docs/troubleshooting.md)
- [Actualizaciones y mantenimiento](docs/maintenance.md)
- [Referencia de la integración](docs/integration-reference.md)
- [Historial de cambios](CHANGELOG.md)

La documentación técnica principal se mantiene en el [README principal](README.md).

## Origen y licencia

Esta versión mantenida está basada en el proyecto `hass-livoltek` de Adam Lonsdale y conserva su atribución y licencia MIT.
