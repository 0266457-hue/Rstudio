# Tareas de R (Riesgo, Credito y Mercado) - Carlos Roman Ulloa

Resolver las tareas en `.Rmd` apegandose lo mas posible a la forma de resolver del profesor.
No agregar pasos extra que el no usa (`table()`, columnas `_num`, `NULL`, `1-probabilidad`, etc.); solo lo que pide la tarea y con su misma sintaxis. Si la tarea pide conclusiones, escribirlas breves.

- Ruta de datos: `C:/Users/carlos/...` (si el archivo trae otra ruta, solo cambiar el usuario por `carlos`).
- Base principal en `cred` y cada paso en un contenedor nuevo: `cred2`, `cred3`, ...
- Exploracion: `head()` y `tail()`; comprobar filtros con `unique()` y `min()` con comentario `#comprobar`.
- Nombres como el profesor: binaria `loanbin`, perfiles `per1`/`per2`, `perfs`, `mod1`, `predicted_test`, `probabilidad`.
- Filtrar filas primero con todas las columnas (`cred2<-cred[(cond1|cond2)&cond3,]`), luego seleccionar columnas aparte (`cred3<-cred2[,c(...)]`).
- Verificar cada paso con `unique()`, `names()`, `str()` o `summary()`.
- Iniciar el primer chunk con `rm(list = ls())`.
- Variable binaria con `ifelse(...=="Fully Paid",1,0)`; pasar char a num con `as.numeric(as.factor(...))` sobrescribiendo la misma columna (`cred4$term<-as.numeric(as.factor(cred4$term))`), sin crear columnas `_num` ni subconjuntos extra.
- Modelo: `mod1<-glm(y~x1+x2,data=cred3,family=binomial())` y `summary(mod1)`.
- Perfiles: vectores con `c()`, `rbind()`, `as.data.frame()` y `names(perfs)[1:n]<-c(...)`.
- Probabilidad: `predicted_test<-predict(mod1,perfs)` y `probabilidad<-exp(predicted_test)/(1+exp(predicted_test))`.
- Despues de la probabilidad, mostrar `mod1$coefficients` y `exp(mod1$coefficients)`.
- Si un monto viene mal escrito (ej. "30,00"), el profesor lo toma como 3,000.
- CETES 28 dias usado por el profesor: 6.01.
- Codigo sin espacios en la asignacion (`x<-c(...)`) y comentarios cortos con `#`.
