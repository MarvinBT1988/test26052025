# Evaluando tus Habilidades de POO en Java

### Estructura del proyecto

![image](https://github.com/user-attachments/assets/775b6863-3787-4336-8d06-b8e552c193dd)

## IFigura.java

```java
package figuras;

public interface IFigura {
    double calcularArea();
    String obtenerInformacion();
}
```
## ColorForma.java

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

## FormaGeometrica.java

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
## Circulo.java
```java
package figuras;

public class Circulo extends FormaGeometrica {
    private double radio;

    public Circulo() {
        super();
    }

    public Circulo(String nombre, double radio) {
        super(nombre);
        this.radio = radio;
    }

    public double getRadio() {
        return radio;
    }

    public void setRadio(double radio) {
        this.radio = radio;
    }

    public int obtenerValorArray(int a, int b, int c, int d) {
        int r = 0;
        int[] circuloArray = { d, c, b, a };
        for (int i = 0; i < circuloArray.length; i++) {
            if (i == 2) {
                r = circuloArray[i];
                break;
            }
        }
       return r;
    }
}

```
