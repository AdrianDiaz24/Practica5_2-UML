![foto del diagrama](https://github.com/AdrianDiaz24/Practica5_2-UML/blob/main/Captura%20de%20pantalla%20(54).png)


### a) Una breve lista de los conceptos que te has encontrado en los diagramas UML que se asemejan a los conceptos de programación orientada a objetos. Por ejemplo: Clases: GestorPedidos

- Clases: represetan las partes de la transacción que queremos recoger en el sistema.
  - Cliente, es una clase que representa a los clientes que realizan los pedidos, es decir, a las intancias de tipo Cliente cuya información queremos almacenar (atributos) y que poseen unos comportamientos o métodos que son las gestiones necesarias para realizar un pedido.
  - Pedido, es una clase que representa los pedidos que pueden realizarse por los clientes, es decir, es una instancia, un objeto de tipo Pedido que almacena la información necesaria sobre la compra que realizan los clientes, así como posee unos métodos que son las operaciones necesarias para dicha compra.
  - Producto, es una clase que representa a los productos que pueden ser parte de un pedido, son, por tanto, los objetos de tipo Producto que almacenan los datos de cada producto que puede comprar un cliente. También poseen sus propios métodos, necesario para la gestión de la compra.
  - Pago, es una clase que representa los pagos que pueden realizarse para un mismo pedido, es decir, son los métodos necesarios, así como los datos de interes sobre dichos plazos y formas de pago.
  - Fecha, es una clase que recoge el día, mes y año de una fecha en concreto, teniendo, a su vez, un método o comportamiento de la clase que verifique que dicha fecha sea válida.

- Atributos: representan, dentro de cada clase, la información que queremos almacenar de cada parte de la gestión de una compra. Son variables que, en algunos casos, pueden modificar su valor mediente actualizaciones. Algunos ejemplos de los atributos son:
   - Email, dentro de la clase Cliente tenemos dicho atributo para almacenar el correo del usuario para poder tramitar su pedido e informarle de las actualizaciones.
   - Stock, dentro de la clase Producto para almacenar la cantidad existente de ese producto determinado y, mediante los métodos, comprobar si el pedido puede ser realizado.
 
- Métodos: se tratan del comportamiento o funciones necesarias, dentro de cada clase, para que la realización de un pedido pueda ser llevada a cabo. Algunos ejemplos:

- Herencia: podríamos hablar de herencia en la clase de FormaPago si no fuera un enum, sino una clase abstracta, ya que contaría con las subclases de Card, Cash y Cheque, las cuales heredarían de la clase FormaPago una interfaz común, aunque permitiendo que tengan sus propias implementación específica.

- Enumeración: lo encontramos tanto en FormaPago como en EstadoPedido, los cuales tiene predefinido unos valores concretos que son los únicos que puede tomar la clase.

- Relaciones entre clases: las relaciones entre las clases pueden ser de asociación, agregación o composición, y nos hablan de cómo se relaciona la información y se conectan los métodos en el sistemas que estamos definiendo.
  - Cliente y Pedido, un cliente puede realizar muchos pedidos, pero un pedido sólo puede estar asociado a un cliente. Con esto sabemos la multiplicidad de la relación y el tipo, en este caso de agregación, ya que pedidos se agregan a un cliente determinado.
  - Pedido y Producto, un pedido puede contar con uno o varios productos, y un producto puede aparecer en uno o varios pedidos. En este caso el tipo de relación es de composición.
  - Pedido y Pago, un pedido puede tener varios pagos registrados, y un pago está asociado a un sólo pedido. En este caso, la relación es de tipo asociación.


## b) Explicación de la herramienta que has utilizado parra generar el diagrama UML, y si la has contrastado con otra y conclusiones de porque has elegido esa.

He utilizado Dia para la generación del diagrama UML y he contrastado esta herramienta con Lucidchart. A continuación, presento una breve explicación de ambas herramientas y las razones por las que me decanté por Dia:

Dia

  Ventajas:
  
  Gratuita y de código abierto, sin necesidad de suscripciones.
  Ofrece una amplia variedad de formas UML y otras figuras estándar.
  Soporta formatos de exportación populares como PNG, SVG y PDF.
  Ligera y fácil de instalar.
  Inconvenientes:
  
  Interfaz de usuario algo desactualizada y menos intuitiva.
  Menor integración con herramientas colaborativas en la nube.
  Menor cantidad de plantillas prediseñadas.

Lucidchart

  Ventajas:
  
  Interfaz moderna, intuitiva y fácil de usar.
  Colaboración en tiempo real con otros usuarios.
  Amplia gama de plantillas listas para usar.
  Integración con Google Workspace, Microsoft y otras plataformas.
  
  Inconvenientes:
  
  Modelo freemium, con restricciones en la versión gratuita.
  Requiere conexión a Internet para acceder a todas sus funciones.
  Dependencia del navegador y del entorno web.

Conclusión
 
  Elegí Dia debido a su carácter gratuito, independencia de conexión a Internet y capacidad para exportar en múltiples         formatos. Aunque Lucidchart ofrece una experiencia de usuario más moderna y colaborativa, su modelo de suscripción y         limitaciones en la versión gratuita hicieron que no fuera la opción más adecuada para un proyecto sin requerimientos         complejos.



## c) Una explicación sobre la conversión del diagrama UML al código.


Clases y atributos:

Se crea las clases del diagrama en kotlin con todos sus atributos

Relaciones entre clases:

Para reflejar las relaciones hacemos que las clases pidan a su vez otras clases para construirse

La clase Cliente tiene una lista de pedidos (val pedidos = mutableListOf<Pedido>()), lo que refleja la relación de un cliente con muchos pedidos.

Enumeraciones:

Las clases EstadoPedido y FormaPago se han representado como enums en el código. 

Métodos:

Se crean en las clases los metodos como funciones dentro de estas



