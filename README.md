# Evaluando tus Habilidades de POO en Java

### Estructura del proyecto

![image](https://github.com/user-attachments/assets/3b32c1cb-d013-466d-8c9a-cefb884bd18e)


## Figura.java

```java
package figuras;

public interface Figura {
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

public class FormaGeometrica implements Figura {
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
        b -= 2;
        c += 3;
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

## Cuadrado.java
```java
package figuras;

public class Cuadrado extends FormaGeometrica {
    private double lado;

    public Cuadrado() {
        super();
    }

    public Cuadrado(String nombre, double lado) {
        super(nombre);
        this.lado = lado;
    }

    public double getLado() {
        return lado;
    }

    public void setLado(double lado) {
        if (lado < 0) {
            lado = 2;
        }
        this.lado = lado;
    }

    @Override
    public double calcularArea() {
        return lado * lado;
    }

    public byte obtenerValorColor() {
        ColorForma color = this.getColor();
        byte a = 0;
        switch (color) {
            case ROJO:
                a = 6;
                break;
            case VERDE:
                a = 4;
                break;
            case AZUL:
                a = 2;
                break;
            case AMARILLO:
                a = 5;
                break;
            case BLANCO:
                a = 3;
                break;
             case NEGRO:
                a = 1;
                break;
        }
        return a;
    }
}


```

## Rectangulo.java
```java
package figuras;

public class Rectangulo extends FormaGeometrica {
    private double base;
    private double altura;

    public Rectangulo() {
        super();
    }

    public Rectangulo(String nombre, double base, double altura) {
        super(nombre);
        this.base = base;
        this.altura = altura;
    }

    public double getBase() {
        return base;
    }

    public void setBase(double base) {
        this.base = base;
    }

    public double getAltura() {
        return altura;
    }

    public void setAltura(double altura) {
        this.altura = altura;
    }

    @Override
    public double calcularArea() {
        return base * altura;
    }

    @Override
    public String obtenerInformacion() {
        String base = super.obtenerInformacion() +" " + this.base;
        return base;
    }
}


```
## Main.java
```java
import figuras.Circulo;
import figuras.ColorForma;
import figuras.Rectangulo;
import figuras.Cuadrado;

public class Main {
    public static void main(String[] args) {

        Circulo ci1 = new Circulo("Circulo A", 5.0);
        ci1.setColor(ColorForma.ROJO);

        Rectangulo re1 = new Rectangulo("Rectangulo A", 2, 4);
        re1.setColor(ColorForma.VERDE);
        double base = re1.getBase();
        double altura = re1.getAltura();
        base++;
        altura++;

        Cuadrado cu1 = new Cuadrado("Cuadrado A", 3);
        cu1.setColor(ColorForma.NEGRO);

        Circulo ci2 = new Circulo();
        ci2.setNombre("Circulo B");
        ci2.setColor(ColorForma.BLANCO);
        ci2.setRadio(3.0);

        Rectangulo re2 = new Rectangulo();
        re2.setColor(ColorForma.AZUL);
        re2.setNombre("Rectangulo B");
        re2.setBase(base);
        re2.setAltura(altura);

        Cuadrado cu2 = new Cuadrado();
        cu2.setNombre("Cuadrado B");
        cu2.setColor(ColorForma.AMARILLO);
        cu2.setLado(-5.0);

        Circulo ci3 = new Circulo("Circulo C", 7.0);
        ci3.setColor(ci1.getColor());
        // Imprimir los datos de los objetos

        System.out.println("Area_1 es: " + ci1.calcularArea());

        int valorArray = ci2.obtenerValorArray(7, 8, 5, 3);
        System.out.println("Valor del array es: " + valorArray);

        byte valorColor = cu1.obtenerValorColor();
        System.out.println("Valor del color es: " + valorColor);

        System.out.println("Area_2 es: " + cu2.calcularArea());

        System.out.println("Informacion_1 es: " + re1.obtenerInformacion());

        System.out.println("Area_3 es: " + re2.calcularArea());

        System.out.println("Informacion_2 es: " + ci3.obtenerInformacion());

    }
}



```
