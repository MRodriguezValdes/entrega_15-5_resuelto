# entrega_15-5_resuelto
```java
package objetos_to_ex;

public abstract class Persona {

	private String name;
	private int edad;
	private String DNI = "";
	private Character sexo = 'M';
	private float peso;
	private float altura;

	public Persona() {
		this.name = "?";
		this.edad = 0;
		this.DNI = "000000000";
		this.peso = 0f;
		this.altura = 0f;
	}

	public Persona(String name, int edad, Character sexo) {
		this.setName(name);
		this.setEdad(edad);
		this.setSexo(sexo);
		this.DNI = "000000000";
		this.peso = 0f;
		this.altura = 0f;

	}

	public Persona(String name, int edad, String DNI, Character sexo, float peso, float altura) {
		this.setName(name);
		this.setEdad(edad);
		this.setDNI(DNI);
		this.setSexo(sexo);
		this.setPeso(peso);
		this.setAltura(altura);
	}

//	Getters and Setters
	public String getName() {
		return name;
	}

	public void setName(String name) {
		this.name = name;
	}

	public int getEdad() {
		return edad;
	}

	public void setEdad(int edad) {
		this.edad = edad;
	}

	public String getDNI() {
		return DNI;
	}

	public void setDNI(String dNI) {
		DNI = dNI;
	}

	public Character getSexo() {
		return sexo;
	}

	public void setSexo(Character sexo) {
		this.sexo = sexo;
	}

	public float getPeso() {
		return peso;
	}

	public void setPeso(float peso) {
		this.peso = peso;
	}

	public float getAltura() {
		return altura;
	}

	public void setAltura(float altura) {
		this.altura = altura;
	}

//	METODOS
	public void calcularIMC() {
		double IMC = peso / Math.pow(this.getAltura(), 2);
		if (IMC < 18.5d) {
			System.out.println("Esta por debajo de su peso");
		} else if (18.5d <= IMC && IMC <= 24.9d) {
			System.out.println("Esta en su peso ideal");
		} else if (25d <= IMC && IMC <= 29.9d) {
			System.out.println("La persona tiene sobrepeso");
		} else
			System.out.println("Tiene obesidad");
	}

	public boolean esMayorDeEdad() {
		return this.getEdad() >= 18;
	}

//  Abstrac Metods
	public abstract boolean comprobarSexo(Character sexo);

// TOSTRING
	@Override
	public String toString() {
		return "Persona [name=" + name + ", edad=" + edad + ", DNI=" + DNI + ", sexo=" + sexo + ", peso=" + peso
				+ ", altura=" + altura + "]";
	}

}
```
# Ejercicio 5

Explica brevemente como replantearías tu código si hubiera varios tipos de personas de
naturaleza similar con pequeñas variaciones entre ellas, por ejemplo: estudiante y
profesor. En relación a esto, ¿en qué caso o casos podríamos utilizar la palabra
reservada super?


Si nos encontraramos en la situacion planteada en el ejercicio,mantendria la clase Persona como clase abstracta,
porque la intencion no seria crear un objeto persona, nos permitiria englobar un conpecto. En cuanto a las demas
clases emplearia la herencia.Super se puede emplear en las clases hijas , para ser referencia al constructor y
metodos de la clase padre (Persona).


# Ejercicio 6

¿Son realmente neceserios los getters y los setters en este enunciado? Justifica tu
respuesta.

Realamente depende de el contexto que nos encontremos. En el caso de la clase Persona es algo relativo, pero 
en general son necesarios para acceder a los atributos  a los que deseamos que se tenga acceso.Los setters son 
ampliamente empleados en los contructores de los objetos, ya que se considera una buena practica , se pueden emplear
para realizar control de errores, etc.



