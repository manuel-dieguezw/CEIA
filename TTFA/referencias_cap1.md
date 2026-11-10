# Referencias — Capítulo 1

Estado del relevamiento de referencias para el Capítulo 1.
Cada afirmación del capítulo necesita al menos una cita en formato IEEE.

---

## Referencias propuestas (verificar acceso independientemente)

### [R1] Zhu & Nandi 2015 — libro de referencia del área ✅ ELEGIDA para afirmación 1

> Z. Zhu y A. K. Nandi, *Automatic Modulation Classification: Principles, Algorithms and Applications*, Wiley-IEEE Press, 2015. ISBN: 978-1-118-87316-0

Cubre: definición de AMC, aplicaciones, métodos clásicos y sus limitaciones.
Usar para: afirmaciones 1 (definición), 2 (aplicaciones), 5 (métodos tradicionales).

---

### [R2] Dobre et al. 2007 — descartada (reemplazada por R1)

> O. A. Dobre, A. Abdi, Y. Bar-Ness y W. Su, "Survey of automatic modulation classification techniques: classical approaches and new trends," *IET Communications*, vol. 1, no. 2, pp. 137–156, 2007. DOI: 10.1049/iet-com:20050176

---

### [R3] O'Shea, Corgan & Clancy 2016 — introducción del DL en AMC

> T. J. O'Shea, J. Corgan y T. C. Clancy, "Convolutional radio modulation recognition networks," in *Proc. Engineering Applications of Neural Networks (EANN)*, 2016. arXiv: 1602.04105

Acceso libre: https://arxiv.org/abs/1602.04105
Cubre: CNN sobre IQ crudas supera métodos clásicos, introducción del dataset RadioML 2016.10a.
Usar para: afirmaciones 6 (DL supera clásicos), 7 (CNN sobre IQ), 12 (RadioML 2016.10a).
~3000 citas en Google Scholar.

---

### [R4] O'Shea, Roy & Clancy 2018 — evaluación en RadioML

> T. J. O'Shea, T. Roy y T. C. Clancy, "Over-the-air deep learning based radio signal classification," *IEEE Journal of Selected Topics in Signal Processing*, vol. 12, no. 1, pp. 168–179, 2018. DOI: 10.1109/JSTSP.2018.2797022

Cubre: resultados sobre RadioML, comparativa de arquitecturas, >80% accuracy a SNR≥0 dB.
Usar para: afirmaciones 11 (>80% accuracy), 13 (caída a bajo SNR).

---

### [R5] Peng et al. 2019 — redes recurrentes para AMC

> S. Peng, H. Jiang, H. Wang, H. Alwageed y Y.-D. Yao, "Modulation classification based on signal constellation diagrams and deep learning," *IEEE Transactions on Neural Networks and Learning Systems*, vol. 30, no. 3, pp. 718–727, 2019. DOI: 10.1109/TNNLS.2018.2850703

Cubre: uso de LSTM/GRU para capturar dependencias temporales en AMC.
Usar para: afirmación 10 (LSTM y GRU en AMC).

---

### [R6] Kim et al. 2018 — arquitecturas avanzadas AMC

> B. Kim, J. Kim, H. Tae y J. Choi, "Automatic modulation classification using recurrent neural networks," in *Proc. IEEE 3rd International Conference on Cloud and Big Data Computing*, 2018. DOI: 10.1109/LCOMM.2018.2792026

Cubre: comparativa de arquitecturas, complejidad creciente.
Usar para: afirmaciones 8 (arquitecturas complejas), 10 (redes recurrentes).

---

### [R7] O'Shea & Hoydis 2017 — DL para la capa física

> T. J. O'Shea y J. Hoydis, "An introduction to deep learning for the physical layer," *IEEE Transactions on Cognitive Communications and Networking*, vol. 3, no. 4, pp. 563–575, 2017. DOI: 10.1109/TCCN.2017.2758370

Cubre: paradigma DL en comunicaciones, radio cognitiva, SDR.
Usar para: afirmación 9 (estado del arte dominado por DL), motivación de SDR.

---

## Mapeo afirmaciones → referencias

| # | Afirmación (extracto del texto) | Referencia |
|---|--------------------------------|------------|
| 1 | Definición de AMC: identificar modulación sin info previa | R1 |
| 2 | Aplicaciones: monitoreo espectro, radio cognitiva, etc. | R1 |
| 3 | Formato IQ: componentes en fase y cuadratura | R1 (o sin cita, es definición técnica estándar) |
| 4 | SNR como variable condicionante del desempeño | R4 |
| 5 | Métodos tradicionales: FFT, autocorrelación, momentos | R1 |
| 6 | DL superó métodos clásicos | R3 |
| 7 | CNN sobre muestras IQ crudas | R3 |
| 8 | Arquitecturas de creciente complejidad | R6, R7 |
| 9 | Estado del arte dominado por DL | R7 |
| 10 | CNN, LSTM, GRU, TCN en AMC | R3, R5, R6 |
| 11 | >80% accuracy a SNR≥0 dB en RadioML 2016.10a | R4 |
| 12 | RadioML 2016.10a como dataset de referencia | R3 |
| 13 | Caída de desempeño a bajo SNR — problema abierto | R4 |

---

## Pendientes

- [ ] Verificar acceso a R1 (libro Zhu & Nandi) — ISBN 978-1-118-87316-0
- [ ] Verificar DOI de R4 (O'Shea 2018 IEEE JSTSP)
- [ ] Verificar DOI de R5 (Peng 2019 IEEE TNNLS)
- [ ] Verificar DOI de R6 (Kim 2018) — el DOI asignado puede no coincidir exactamente
- [ ] Agregar referencias confirmadas a `references.bib`
- [ ] Agregar tabla comparativa en sección 1.3 (TODO en Chapter1.tex)
- [ ] Escribir resumen (abstract) — entrega máx. 02/NOV
- [ ] Completar portada.tex con título, autor, director, codirector

## Estado del arte: DL-AMC (agregado 10/NOV)

- Referencia: F. U. Rehman, Q. Abbas y M. K. Shehzad, "DL-AMC: Deep Learning for Automatic Modulation Classification", arXiv:2504.08011, v1, 10 abr 2025. DOI 10.48550/arXiv.2504.08011. Clave: `rehman2025dlamc`.
- Estado: leída completa. Preprint sin revisión verificable.
- Diagramas de ojo separados en I y Q: sec. II-A, p. 2, Fig. 1 (p. 3).
- ResNet-18, ResNet-50 y MobileNetV2: abstract y sec. II-B, p. 2-3.
- 14 modulaciones, 420x10^3 tramas, SNR de -20 a 30 dB: sec. II-C, p. 3-4 (nota al pie 3).
- 93,6% a -20 dB frente a DBN 10%, RNN 48%, LSTM 12% y CLDNN 12%: sec. III-A, p. 4.
- Advertencia: sus referencias [13] y [14] (RNN y LSTM) son trabajos de predicción de canal MIMO.

## Agregadas el 10/NOV (leídas completas)

- `rajendran2018distributed`: S. Rajendran, W. Meert, D. Giustiniano, V. Lenders y S. Pollin, "Deep Learning Models for Wireless Signal Classification with Distributed Low-Cost Spectrum Sensors", arXiv:1707.08908 v2, 2018.
  - Decisión teórica óptima pero costosa, sin robustez ante canal desconocido; selección manual de características tediosa: sec. I, p. 1-2.
  - I = A cos(phi), Q = A sin(phi): sec. II, p. 3.
  - LSTM de 2 capas sobre amplitud y fase, ~90% de 0 a 20 dB: abstract y sec. V-A, p. 5.
  - LSTM con IQ queda en 9%; CNN con amplitud/fase no mejora: sec. V-A, p. 6.
- `ghasemi2019spectrum`: A. Ghasemi, C. Parekh y P. Guinand, "Spectrum Awareness Under Co-Channel Usage Via Deep Temporal Convolutional Networks", Communications Research Centre, Ottawa, 2019 (congreso no confirmado).
  - Convoluciones causales dilatadas, campo receptivo mayor con pocas capas: sec. III, p. 2, Fig. 1.
  - 128 muestras: desempeño similar a CLDNN; 1024 muestras: mejor que CLDNN sobre -18 dB y 100% sobre 0 dB: sec. IV-A, p. 3, Fig. 3 y 4.
- `oshea2016convolutional` (releída): modelo de señal r(t) = s(t) c + n(t), sec. 2, p. 2; efectos reales, p. 2-3.
