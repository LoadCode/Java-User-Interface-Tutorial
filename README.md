## Interfaces Gráficas en Java

### Índice
-	[El JFrame y las Ventanas](#JFrameyVentanas)
	-	[Métodos Relevantes del JFrame](#MetodosRelevantesDeJFrame)
	-	[Contenedor del JFrame](#ContenedorDelJFrame)

-	[Widgets (Elementos de Interfaz)](#Widgets)
	-	[Los Botones (JButton)](#JButton)
	-	[Etiquetas de Texto (JLabel)](#JLabel)
	-	[Entradas de Texto (JTextField)](#JTextField)
	-	[Cajas de Verificación (JCheckBox)](#JCheckBox)
	-	[Botones Radiales (JRadioButton)](#JRadioButton)
	-	[Listas Desplegables]()

-	[Layouts](#Layouts)
	- [BorderLayout]()
	- [GridLayout]()
	- [FlowLayout]()

-	[Selección de Archivos y Directorios]()
-	[Cajas de Información]()

###<a id="JFrameyVentanas">JFrame y las Ventanas</a>

Una clase que defina una ventana deberá heredar de la clase ***JFrame***, es decir que como plantilla, si tenemos una clase llamada **Window** que definirá una ventana de nuestro programa, entonces su definición debe tener el siguiente formato:

```java
public class Window extends JFrame
{
	/*Atributos*/
    /*Métodos  */
}
```
A su vez, cabe anotar que la clase **JFrame** puede ser utilizada, importando el paquete **swing** donde se encuentra declara, esto lo hacemos con la siguiente línea:
```java
import javax.swing.JFrame
```
Posee 3 tipos de constructor de los cuales los dos siguientes son las formas más utilizadas: `JFrame();` o `JFrame(String titulo)`

####<a id="MetodosRelevantesDeJFrame">Métodos relevantes de JFrame</a>
A continuación, listaremos y presentaremos una breve descripción de algunos de los métodos más comunes de **JFrame** que utilizaremos en la creación de interfaces gráficas:
*	**.setBounds(posX, posY, Ancho, Alto)**: Se configura la posición en la cual aparecerá inicialmente.
*	**.setVisible(bool)**: Si su parámetro tiene presenta un valor **true**, hace visible el contendio del **JFrame** en pantalla.
*	**.add(widget)**: Agrega un elemento al contenido del **JFrame**.
*	**.setSize(ancho, alto)**: Modifica las dimensiones de la ventana que se está manipulando.
*	**.setTitle(Título)**: Con esto se indica el título que llevará la ventana en su barra superior (la barra de título).
*	**.setLayout(layoutType)**: Configura el tipo de *layout* que deseamos utilizar dentro del JFrame (**ver: Layouts**).
*	**.setResizable(bool)**: Cuento su argumento vale *true*, se le permite a la ventana modificar sus dimensiones, cuando el parámetro vale *false* no se puede modificar el tamaño de la ventana en cuestión.
*	**.setDefaultCloseOperation(acción_cierre)**: Con esta línea se logra que se termine el proceso cuando la ventana se cierre.	Las acciones de cierre pueden ser las siguientes:

	*	**JFrame.EXIT_ON_CLOSE**: Abandona la aplicación.
	*	**JFrame.DISPOSE_ON_CLOSE**: Libera los recursos asociados a la ventana.
	*	**JFrame.DO_NOTHING_ON_CLOSE**: No hace nada.
	*	**JFrame.HIDE_ON_CLOSE**: Cierra la ventana, sin liberar sus recursos.

###<a id="ContenedorDelJFrame">Contenedor del JFrame</a>
Como una anotación adicional, es importante comentar que existen dos formas de utilizar el método **.add( )**, en primer lugar se puede simplemente llamar el método desde el propio objeto *JFrame* para agregar un elemento, por ejemplo, a continuación agregaremos un objeto llamado **btn**:

```java
JFrame myFrame = new JFrame("My Frame");
.
.
.
myFrame.add(btn);
```

La siguiente forma corresponde a trabajar con el *Container* del *JFrame*, es decir, trabajar con un objeto que representa el interior del *JFrame*, el **contenedor de widgets.**
Para hacer uso de los contenedores debemos importar el módulo **Container** del paquete **awt** como se muestra en la siguiente línea:

`import java.awt.Container;`

Para obtener el contenedor o **contentPane** de un **JFrame** utilizamos el método ***.getContentPane( )***. El segmento de código de anterior, puede ser reemplazado por lo siguiente:

```java
JFrame myFrame = new JFrame("My JFrame and Container");
.
.
Container cp = myJFrame.getContentPane( );
cp.add(btn); //Agregamos el elemento al contenedor del JFrame
```

##<a id="Widgets">Widgets (Elementos)</a>
Los widgets son elementos escenciales para nuestras aplicaciones, ya que a través de ellos podremos interactuar con nuestros usuarios y por lo tanto capturar y mostrar información en nuestros programas. Exite una interesante variedad de elementos disponibles en las bibliotecas Java, los más utilizados los presentaremos a continuación. Es importante tener en cuenta que una vez creado y configurado un elemento (*widget*), debería ser *añadido* al **contentPane** de la ventana o *Frame* mediante su método **.add(**widget**)**.

###<a id="JButton">Botón (JButton)</a>
La clase **JButton** nos permite generar objetos de tipo *botón*, mediante los cuales el usuario podrá generar eventos al presionarlos y que nosotros prodremos escuchar para tomar las acciones apropiadas. Posee varios constructores, con mayor frecuencia son utilizados los siguientes: `JButton( )` y `JButton(String texto)`.

Para crear un nuevo botón con la siguiente sintaxis es suficiente:
`JButton btn = new JButton("Saludar");`

Se debe importar el componente *JButton* del paquete *swing* como se muestra a continuación:
`import javax.swing.JButtton;`

###<a id="JLabel">Etiqueta de Texto (JLabel)</a>
###<a id="JTextField">Entrada de Texto (JTextField)</a>
###<a id="JCheckBox">Caja de Verificación (JCheckBox)</a>
###<a id="JRadioButton">Botones de Radio (JRadioButton)</a>
###<a id="ListBox">Listas Desplegables</a>

##<a id="Layouts">Layouts</a>
Los diferentes *layouts* de los que podemos hacer uso en nuestras interfaces se encuentran en el paquete ***awt*** y por lo tanto, para que estén disponibles en nuestros desarrollos debemos agregar líneas con el siguiente formato:

`import java.awt.NombreLayout`

Donde *NombreLayout* puede ser:
*	**BorderLayout:**
*	**GridLayout:**
*	**FlowLayout:**

#####Fuentes:
*	[**Diapositivas: Interfaces Gráficas con Swing**](http://dalila.sip.ucm.es/~manuel/JSW1/Slides/Swing.pdf)
*	[**Github Gist: Ejemplo de creación de una ventana con Swing**](https://gist.github.com/alvareztech/9022849)
*	[**Video Tutorial: Layouts en Java**](https://www.youtube.com/watch?v=mx5eZwlcg78)
####