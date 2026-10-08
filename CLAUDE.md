# Tareas de R (Riesgo, Credito y Mercado) - Carlos Roman Ulloa

Resolver las tareas en `.Rmd` siguiendo la forma de resolver del profesor:

- Ruta de datos: `C:/Users/carlos/...` (si el archivo trae otra ruta, solo cambiar el usuario por `carlos`).
- Base principal en `cred` y cada paso en un contenedor nuevo: `cred2`, `cred3`, ...
- Filtrar filas primero con todas las columnas (`cred2<-cred[(cond1|cond2)&cond3,]`), luego seleccionar columnas aparte (`cred3<-cred2[,c(...)]`).
- Verificar cada paso con `unique()`, `names()`, `str()` o `summary()`.
- Variable binaria con `ifelse(...=="Fully Paid",1,0)`; pasar char a num con `as.numeric(as.factor(...))`.
- Modelo: `mod1<-glm(y~x1+x2,data=cred3,family=binomial())` y `summary(mod1)`.
- Perfiles: vectores con `c()`, `rbind()`, `as.data.frame()` y `names(perfs)[1:n]<-c(...)`.
- Probabilidad: `predicted_test<-predict(mod1,perfs)` y `probabilidad<-exp(predicted_test)/(1+exp(predicted_test))`.
- CETES 28 dias usado por el profesor: 6.01.
- Codigo sin espacios en la asignacion (`x<-c(...)`) y comentarios cortos con `#`.
