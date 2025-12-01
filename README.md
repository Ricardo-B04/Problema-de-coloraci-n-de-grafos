# Coloración de Grafos con Algoritmo Genético

## Descripción

Este proyecto implementa un **Algoritmo Genético** para resolver el problema de **Coloración de Grafos** (Graph Coloring Problem). El objetivo es encontrar el número mínimo de colores necesarios para colorear un grafo de 19 nodos, tal que ningún par de nodos adyacentes tengan el mismo color.

## Problema

Se busca una asignación de colores $c: V \rightarrow \{1, 2, ..., N_c\}$ tal que:
- Para toda arista $(u,v) \in E$, se cumple $c(u) \neq c(v)$
- Se minimiza el número de colores utilizados $N_c$ (número cromático $\chi(G)$)

### Grafo de Entrada
- **Número de nodos:** 19
- **Número de aristas:** 41
- **Estructura:** Grafo no dirigido definido por lista de adyacencia

## Algoritmo Genético

### Representación
- **Cromosoma:** Vector entero de longitud 19, donde cada posición representa el color asignado a un nodo.

### Operadores Genéticos
| Operador | Descripción |
|----------|-------------|
| **Selección** | Torneo binario |
| **Cruce** | Uniforme (prob. 0.85) |
| **Mutación** | Cambio de color inteligente (prob. 0.20) |
| **Elitismo** | 2 mejores individuos |

### Función de Fitness
$$\text{fitness}(c) = \text{conflictos} + 0.4 \cdot \text{num\_colores}$$

Donde:
- `conflictos`: Número de aristas con ambos extremos del mismo color
- `num_colores`: Cantidad de colores distintos utilizados

### Parámetros
| Parámetro | Valor |
|-----------|-------|
| Tamaño de población | 100 |
| Generaciones máximas | 500 |
| Prob. cruce | 0.85 |
| Prob. mutación | 0.20 |
| Máx colores inicial | 10 |

## Resultados

El algoritmo encuentra una **coloración válida óptima**:
- **Número cromático:** 4 colores
- **Conflictos:** 0 (coloración perfecta)

## Estructura del Proyecto

```
├── coloracion_grafos_algoritmo_genetico.ipynb  # Notebook principal
├── requirements.txt                             # Dependencias
└── README.md                                    # Este archivo
```

## Requisitos

```bash
pip install -r requirements.txt
```

### Dependencias
- `numpy`
- `matplotlib`
- `networkx`

## Uso

1. Abrir el notebook `coloracion_grafos_algoritmo_genetico.ipynb`
2. Ejecutar todas las celdas secuencialmente
3. Visualizar los resultados y gráficos generados

## Visualizaciones

El notebook genera 4 gráficos:
1. **Evolución del Fitness** por generación
2. **Evolución de Conflictos** por generación
3. **Evolución del Número de Colores** por generación
4. **Grafo Coloreado** con la solución óptima

## Aplicaciones Prácticas

- Asignación de frecuencias en redes móviles
- Horarios de exámenes sin solapamientos
- Asignación de registros en compiladores
- Mapeo de colores en mapas geográficos
- Problemas de planificación y scheduling

## Complejidad

El problema de Coloración de Grafos es **NP-completo** (Karp, 1972). El Algoritmo Genético proporciona soluciones óptimas o cuasi-óptimas en tiempo polinómico razonable.

## Autor

Ricardo B.

## Licencia

Este proyecto es parte del curso de **Algoritmos Matemáticos Bioinspirados** del Tecnológico de Monterrey.
