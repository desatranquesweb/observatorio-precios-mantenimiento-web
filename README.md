# Observatorio de precios del mantenimiento web en España

Datos abiertos del [observatorio de precios del mantenimiento web](https://desatranquesweb.es/observatorio-precios-mantenimiento-web/) de [Desatranques WEB](https://desatranquesweb.es): **140 tarifas públicas de 52 proveedores**, leídas en la página de cada proveedor el 17 de octubre de 2026. Cada fila es un plan, con su precio comparable (al mes y sin IVA), lo que incluye y el enlace a la página consultada.

## Cifras (consulta del 17 de octubre de 2026)

Medianas por nivel. Los proveedores con un solo plan no entran en las medianas por nivel.

**Webs** (106 planes)

| Nivel | Mediana al mes sin IVA | Rango | Planes |
|---|---|---|---|
| Básico | 47,00 € | 15,00 € – 149,00 € | 36 |
| Intermedio | 89,00 € | 30,00 € – 297,00 € | 27 |
| Avanzado | 105,00 € | 29,00 € – 597,00 € | 36 |

**Tiendas online** (34 planes)

| Nivel | Mediana al mes sin IVA | Rango | Planes |
|---|---|---|---|
| Básico | 100,00 € | 22,50 € – 249,00 € | 9 |
| Intermedio | 200,00 € | 40,00 € – 390,00 € | 5 |
| Avanzado | 349,00 € | 42,50 € – 690,00 € | 9 |

El análisis completo, con gráficos, filtros y comparador, está en la [página del observatorio](https://desatranquesweb.es/observatorio-precios-mantenimiento-web/) ([English](https://desatranquesweb.es/en/web-maintenance-pricing-observatory/)).

## Archivos

- [`data/precios-mantenimiento-web.csv`](data/precios-mantenimiento-web.csv): una fila por plan. UTF-8, separado por comas, decimales con punto.
- [`datapackage.json`](datapackage.json): descripción del conjunto de datos en formato [Frictionless Data](https://specs.frictionlessdata.io/data-package/).
- [`CITATION.cff`](CITATION.cff): cómo citarlo.

## Columnas

| Columna | Tipo | Descripción |
|---|---|---|
| `proveedor` | string | Nombre comercial del proveedor. |
| `plan` | string | Nombre del plan tal como aparece en su página. |
| `segmento` | string | Webs o tiendas online (WooCommerce, PrestaShop o «tienda online»). Valores: `web`, `tienda`. |
| `venta_online` | string | ¿La página dice que el plan vale para webs que venden (tienda, cursos, entradas, reservas)? Valores: `si`, `no`, `no-indica`. |
| `nivel` | string | Nivel dentro del proveedor y segmento: el plan más barato es «basico», el más caro «avanzado»; «unico» si solo tiene uno. Valores: `basico`, `intermedio`, `avanzado`, `unico`. |
| `precio_mes_sin_iva_eur` | number | Precio comparable: al mes y sin IVA, en euros (con IVA se divide entre 1,21; si es anual, entre 12). |
| `precio_publicado_eur` | number | Importe publicado tal cual, en la periodicidad y con el IVA que diga la página. |
| `periodicidad` | string | Periodicidad del precio publicado. Valores: `mes`, `año`. |
| `iva_en_pagina` | string | Si el precio publicado incluye el IVA. Valores: `incluido`, `no-incluido`, `no-indica`. |
| `hosting_incluido` | string | Si el plan incluye el hosting. Valores: `si`, `no`, `opcional`, `no-indica`. |
| `horas_incluidas_mes` | number | Horas de trabajo al mes incluidas (cambios o soporte); 0 si no incluye; vacío si no lo dice. |
| `permanencia` | string | Si exige permanencia mínima. Valores: `si`, `no`, `no-indica`. |
| `permanencia_meses` | integer | Meses de permanencia, si la exige y lo indica. |
| `tecnologia` | string | Plataforma a la que se dirige el plan. Valores: `wordpress`, `woocommerce`, `prestashop`, `web`. |
| `url` | string | Página de tarifas consultada. |
| `fecha_consulta` | date | Día en que se leyó la página (AAAA-MM-DD). |
| `nota` | string | Aclaración breve («desde», alta inicial, precio por web…). |

## Cómo se ha hecho

- Solo tarifas públicas: planes de mantenimiento de web o WordPress con precio fijo publicado en euros. Fuera quedan los «precio a consultar», los marketplaces y el hosting sin servicio de mantenimiento.
- Proveedores con titular en España, identificado en su aviso legal (NIF o domicilio).
- Cada cifra se ha leído en la página del proveedor el día de la consulta. No hay datos de memoria ni de terceros.
- Webs y tiendas online por separado. Cuando dos marcas del mismo grupo publican la misma oferta, se cuenta una sola vez.
- Desatranques WEB, que publica el observatorio, está incluido como un proveedor más, en su orden alfabético y con los datos de su propia página.
- Es una muestra de lo que se publica, no del mercado entero: muchos proveedores solo dan precio bajo presupuesto.

La metodología completa está en la [página del observatorio](https://desatranquesweb.es/observatorio-precios-mantenimiento-web/#metodologia-heading).

## Actualización

Cada trimestre se vuelven a consultar todas las páginas y se buscan proveedores nuevos. Cada actualización es un commit con su etiqueta (`datos-AAAA-MM-DD`), así que el historial de precios queda en este repositorio.

¿Has visto un dato desactualizado o quieres que revisemos una tarifa? Abre un *issue* o escribe a contacto@desatranquesweb.es.

## Licencia y cita

[CC BY 4.0](LICENSE): puedes copiar, adaptar y publicar los datos, también con fines comerciales, citando la fuente:

> «Observatorio de precios del mantenimiento web», Desatranques WEB, consulta del 17 de octubre de 2026. https://desatranquesweb.es/observatorio-precios-mantenimiento-web/

---

## English

Open data from the [website maintenance pricing observatory for Spain](https://desatranquesweb.es/en/web-maintenance-pricing-observatory/) by Desatranques WEB: 140 published maintenance prices from 52 providers, checked on 2026-10-17. One row per plan, with the comparable price (monthly, excluding VAT), what it includes and the page checked. Column names and values are in Spanish (see the table above). Licence: CC BY 4.0.
