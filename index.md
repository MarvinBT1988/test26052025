# Evaluando tus Habilidades de POO en Java

### Estructura del proyecto

![image](https://github.com/user-attachments/assets/d28fb036-16e9-458a-b755-ba1678f285dd)

```java
package figuras;

public interface IFigura {
    double calcularArea();
    String obtenerInformacion();
}
```
![image](https://github.com/user-attachments/assets/4408b437-c25f-4f19-a17d-7c76964c4a3b)

```java
package figuras;

public enum ColorForma {
    ROJO,
    VERDE,
    AZUL,
    AMARILLO,
    NEGRO,
    BLANCO
}

```

![image](https://github.com/user-attachments/assets/d9afb164-f443-4ba6-a423-9dc0c87b2d64)

```java
package figuras;

public class FormaGeometrica implements IFigura {
    private String nombre;
    private ColorForma color;

    public FormaGeometrica() {
    }

    public FormaGeometrica(String nombre) {
        this.nombre = nombre;
    }

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }

    public ColorForma getColor() {
        return color;
    }

    public void setColor(ColorForma color) {
        this.color = color;
    }

    @Override
    public String obtenerInformacion() {
        String valor = this.getNombre();
        return valor;
    }

    @Override
    public double calcularArea() {
        double area = 0.1;
        return area;
    }

}

```
