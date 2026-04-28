# Taller de Evaluación de Rendimiento — Sistemas Operativos

**Pontificia Universidad Javeriana · Facultad de Ingeniería · 2026-1**

---

## ¿De qué trata esto?

Este repositorio contiene la entrega del Taller de Evaluación de Rendimiento de la materia Sistemas Operativos. El objetivo fue comparar el rendimiento de dos algoritmos de multiplicación de matrices (**FxT** y **FxC**) implementados en C, ejecutados de forma serial y paralela usando procesos `fork()` e hilos `POSIX pthreads`, sobre 6 máquinas con Linux distintas.

---

## Estructura del repositorio
/src          → Código fuente en C (moduloMM, 4 ejecutables)
/scripts      → Script lanzador.pl para automatizar experimentos
/resultados   → Archivos .dat con los tiempos medidos (30 rep. por config.)
/informe      → Informe final en PDF
---

## Resumen del experimento

- **Algoritmos:** Filas×Transpuesta (FxT) y Filas×Columnas (FxC)
- **Paralelismo:** `fork()` y `pthreads` con 1, 4, 8 y 16 hilos
- **Tamaños de matriz:** 512×512, 1024×1024 y 2048×2048
- **Plataformas:** 5 PCs nativos + 1 máquina virtual (Ubuntu 24.04, GCC -O3)
- **Total de experimentos:** ~1.440 mediciones por máquina (48 configs × 30 repeticiones)

---

## Compilación y uso

    # Compilar
    make all

    # Ejecutar la batería completa de experimentos
    perl scripts/lanzador.pl
