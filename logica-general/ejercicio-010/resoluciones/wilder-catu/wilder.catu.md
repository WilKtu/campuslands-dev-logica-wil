# Explicación del código: Clasificación de un Viaje

## 1. Entradas

La función `clasificarViaje(destino, diasViaje)` recibe los siguientes datos:

- **destino:** lugar al que se realizará el viaje.
- **diasViaje:** cantidad de días que durará el viaje.

---

## 2. Salidas

La función devuelve un objeto con la siguiente información:

- **destino:** nombre del destino.
- **diasViaje:** cantidad de días del viaje (si el dato es válido).
- **clasificacion:** categoría asignada según la duración del viaje.
- **mensaje:** aparece únicamente cuando los días de viaje son negativos.

---

## 3. Caso pequeño resuelto manualmente

### Entrada

```text
Destino: Tikal
Días de viaje: 3
```

### Proceso

1. Verificar que los días de viaje no sean negativos.
2. Comparar la cantidad de días con los rangos establecidos.
3. Como 3 es mayor o igual que 2 y menor que 5, el viaje se clasifica como **Escapada**.

### Salida

```text
Destino: Tikal
Días de viaje: 3
Clasificación: Escapada
```

---

## 4. Pasos de la solución

1. Recibir el destino y la cantidad de días del viaje.
2. Validar que los días de viaje no sean negativos.
3. Si el dato es inválido, devolver un mensaje de error.
4. Comparar la cantidad de días para determinar la clasificación:
   - 10 días o más → Vacaciones largas
   - 5 a 9 días → Vacaciones completas
   - 2 a 4 días → Escapada
   - Menos de 2 días → Excursión
5. Devolver el resultado en un objeto.

---

# 5. Explicación por bloques

## Bloque 1: Definición de la función

```javascript
function clasificarViaje(destino, diasViaje) {
```

Se crea una función que recibe el destino y la duración del viaje en días.

---

## Bloque 2: Validación de datos

```javascript
if (diasViaje < 0) {
    return {
        destino: destino,
        clasificacion: "Dato inválido",
        mensaje: "Los días de viaje no pueden ser negativos."
    };
}
```

Se verifica que la cantidad de días sea un valor válido. Si es negativa, la función devuelve un mensaje de error y finaliza su ejecución.

---

## Bloque 3: Variable de clasificación

```javascript
let clasificacion = "";
```

Se crea una variable donde se almacenará la clasificación del viaje.

---

## Bloque 4: Clasificación del viaje

```javascript
if (diasViaje >= 10) {
    clasificacion = "Vacaciones largas";
} else if (diasViaje >= 5) {
    clasificacion = "Vacaciones completas";
} else if (diasViaje >= 2) {
    clasificacion = "Escapada";
} else {
    clasificacion = "Excursión";
}
```

Se utilizan estructuras `if` y `else if` para clasificar el viaje según su duración.

| Días de viaje | Clasificación |
|--------------:|---------------|
| 10 días o más | Vacaciones largas |
| 5 a 9 días | Vacaciones completas |
| 2 a 4 días | Escapada |
| Menos de 2 días | Excursión |

---

## Bloque 5: Retorno del resultado

```javascript
return {
    destino: destino,
    diasViaje: diasViaje,
    clasificacion: clasificacion
};
```

Se devuelve un objeto con el destino, los días de viaje y la clasificación obtenida.

---

## Bloque 6: Pruebas

El programa realiza dos pruebas para comprobar su funcionamiento.

### Prueba normal

```javascript
const prueba1 = clasificarViaje("Antigua Guatemala", 6);
```

**Resultado esperado**

```text
Destino: Antigua Guatemala
Días de viaje: 6
Clasificación: Vacaciones completas
```

---

### Caso borde

```javascript
const prueba2 = clasificarViaje("Lago de Atitlán", 1);
```

**Resultado esperado**

```text
Destino: Lago de Atitlán
Días de viaje: 1
Clasificación: Excursión
```

---

# 6. Implementación

La solución consiste en una función que:

- Recibe el destino y los días del viaje.
- Valida que la cantidad de días sea correcta.
- Clasifica el viaje utilizando estructuras `if` y `else if`.
- Devuelve un objeto con toda la información del viaje.

Esta implementación es sencilla, eficiente y permite modificar fácilmente los rangos de clasificación si cambian los criterios de duración.

---

# 7. Pruebas

## Pruebas del código

| Destino | Días de viaje | Clasificación |
|----------|--------------:|------------------------|
| Antigua Guatemala | 6 | Vacaciones completas |
| Lago de Atitlán | 1 | Excursión |

---

## Caso inventado

### Entrada

```text
Destino: Semuc Champey
Días de viaje: 12
```

### Resultado esperado

```text
Destino: Semuc Champey
Días de viaje: 12
Clasificación: Vacaciones largas
```

---

# Conclusión

El programa clasifica correctamente un viaje según la cantidad de días de duración. Además, valida que el número de días sea un dato válido y devuelve un objeto con la clasificación correspondiente, facilitando la organización de viajes según su duración.