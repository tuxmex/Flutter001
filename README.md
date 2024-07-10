### Paso 1: Configuración Inicial

1. **Crea el proyecto**:

   ```bash
   flutter create my_flutter_app
   ```

2. **Navega al directorio del proyecto**:

   ```bash
   cd my_flutter_app
   ```

3. **Código básico inicial**:

   ```dart
   import 'package:flutter/material.dart';

   void main() {
     runApp(const MainApp()); // Llama a la clase principal de la aplicación
   }

   class MainApp extends StatelessWidget {
     const MainApp({super.key});

     @override
     Widget build(BuildContext context) {
       return const MaterialApp(
         home: Scaffold(
           body: Center(
             child: Text('Hello, World!'), // Muestra un texto en el centro de la pantalla
           ),
         ),
       );
     }
   }
   ```

4. **Ejecuta la aplicación**:

   ```bash
   flutter run
   ```

### Paso 2: Agregar AppBar

1. **Modifica `lib/main.dart` para agregar AppBar**:

   ```dart
   import 'package:flutter/material.dart';

   void main() {
     runApp(const MainApp()); // Llama a la clase principal de la aplicación
   }

   class MainApp extends StatelessWidget {
     const MainApp({super.key});

     @override
     Widget build(BuildContext context) {
       return MaterialApp(
         home: Scaffold(
           appBar: AppBar(
             title: const Text('App Title'), // Título en la AppBar
           ),
           body: const Center(
             child: Text('Hello, World!'), // Muestra un texto en el centro de la pantalla
           ),
         ),
       );
     }
   }
   ```

2. **Ejecuta la aplicación para ver la AppBar con el título**.

### Paso 3: Agregar Drawer

1. **Modifica `lib/main.dart` para agregar Drawer**:

   ```dart
   import 'package:flutter/material.dart';

   void main() {
     runApp(const MainApp()); // Llama a la clase principal de la aplicación
   }

   class MainApp extends StatelessWidget {
     const MainApp({super.key});

     @override
     Widget build(BuildContext context) {
       return MaterialApp(
         home: Scaffold(
           appBar: AppBar(
             title: const Text('App Title'), // Título en la AppBar
           ),
           drawer: const Drawer(), // Añade un Drawer al lado izquierdo
           body: const Center(
             child: Text('Hello, World!'), // Muestra un texto en el centro de la pantalla
           ),
         ),
       );
     }
   }
   ```

2. **Ejecuta la aplicación para ver el Drawer**.

### Paso 4: Agregar FloatingActionButton

1. **Modifica `lib/main.dart` para agregar FloatingActionButton**:

   ```dart
   import 'package:flutter/material.dart';

   void main() {
     runApp(const MainApp()); // Llama a la clase principal de la aplicación
   }

   class MainApp extends StatelessWidget {
     const MainApp({super.key});

     @override
     Widget build(BuildContext context) {
       return MaterialApp(
         home: Scaffold(
           appBar: AppBar(
             title: const Text('App Title'), // Título en la AppBar
           ),
           drawer: const Drawer(), // Añade un Drawer al lado izquierdo
           body: const Center(
             child: Text('Hello, World!'), // Muestra un texto en el centro de la pantalla
           ),
           floatingActionButton: FloatingActionButton(
             onPressed: () {}, // Acción al presionar el botón
             child: const Icon(Icons.add), // Icono del botón
           ),
         ),
       );
     }
   }
   ```

2. **Ejecuta la aplicación para ver el FloatingActionButton**.

### Paso 5: Agregar BottomNavigationBar

1. **Modifica `lib/main.dart` para agregar BottomNavigationBar**:

   ```dart
   import 'package:flutter/material.dart';

   void main() {
     runApp(const MainApp()); // Llama a la clase principal de la aplicación
   }

   class MainApp extends StatelessWidget {
     const MainApp({super.key});

     @override
     Widget build(BuildContext context) {
       return MaterialApp(
         home: Scaffold(
           appBar: AppBar(
             title: const Text('App Title'), // Título en la AppBar
           ),
           drawer: const Drawer(), // Añade un Drawer al lado izquierdo
           body: const Center(
             child: Text('Hello, World!'), // Muestra un texto en el centro de la pantalla
           ),
           floatingActionButton: FloatingActionButton(
             onPressed: () {}, // Acción al presionar el botón
             child: const Icon(Icons.add), // Icono del botón
           ),
           bottomNavigationBar: BottomNavigationBar(
             items: const [
               BottomNavigationBarItem(
                 icon: Icon(Icons.home, color: Colors.purple), // Icono y color del item Home
                 label: "Home", // Etiqueta del item Home
               ),
               BottomNavigationBarItem(
                 icon: Icon(Icons.person, color: Colors.orange), // Icono y color del item Account
                 label: "Account", // Etiqueta del item Account
               )
             ],
           ),
         ),
       );
     }
   }
   ```

2. **Ejecuta la aplicación para ver el BottomNavigationBar**.

### Paso 6: Crear y Agregar el Widget `Home`

1. **Crea el archivo `lib/home.dart`**:

   ```dart
   import 'package:flutter/material.dart';

   class Home extends StatefulWidget {
     const Home({super.key});

     @override
     State<Home> createState() => _HomeState();
   }

   class _HomeState extends State<Home> {
     var messageText = TextEditingController(); // Controlador para el TextField
     String showMessage = ""; // Variable para mostrar el mensaje

     @override
     Widget build(BuildContext context) {
       return Column(
         children: [
           TextField(
             controller: messageText, // Vincula el controlador al TextField
           ),
           ElevatedButton(
             onPressed: () {
               setState(() => showMessage = messageText.text); // Actualiza el mensaje mostrado
             },
             child: const Text("Show Message") // Texto del botón
           ), 
           Center(
             child: Text(showMessage, textDirection: TextDirection.ltr), // Muestra el mensaje
           ),
         ],
       );
     }
   }
   ```

2. **Modifica `lib/main.dart` para incluir el widget `Home`**:

   ```dart
   import 'package:flutter/material.dart';
   import 'package:my_flutter_app/home.dart'; // Importa el archivo home.dart

   void main() {
     runApp(const MainApp()); // Llama a la clase principal de la aplicación
   }

   class MainApp extends StatelessWidget {
     const MainApp({super.key});

     @override
     Widget build(BuildContext context) {
       return MaterialApp(
         home: Scaffold(
           appBar: AppBar(
             title: const Text('App Title'), // Título en la AppBar
           ),
           drawer: const Drawer(), // Añade un Drawer al lado izquierdo
           body: const Center(
             child: Home(), // Añade el widget Home al cuerpo del Scaffold
           ),
           floatingActionButton: FloatingActionButton(
             onPressed: () {}, // Acción al presionar el botón
             child: const Icon(Icons.add), // Icono del botón
           ),
           bottomNavigationBar: BottomNavigationBar(
             items: const [
               BottomNavigationBarItem(
                 icon: Icon(Icons.home, color: Colors.purple), // Icono y color del item Home
                 label: "Home", // Etiqueta del item Home
               ),
               BottomNavigationBarItem(
                 icon: Icon(Icons.person, color: Colors.orange), // Icono y color del item Account
                 label: "Account", // Etiqueta del item Account
               )
             ],
           ),
         ),
       );
     }
   }
   ```

3. **Ejecuta la aplicación para ver el widget `Home`**.

### Paso 7: Personalizar el AppBar

1. **Modifica `lib/main.dart` para agregar íconos en la AppBar**:

   ```dart
   import 'package:flutter/material.dart';
   import 'package:my_flutter_app/home.dart'; // Importa el archivo home.dart

   void main() {
     runApp(const MainApp()); // Llama a la clase principal de la aplicación
   }

   class MainApp extends StatelessWidget {
     const MainApp({super.key});

     @override
     Widget build(BuildContext context) {
       return MaterialApp(
         home: Scaffold(
           appBar: AppBar(
             title: const Text('App Title'), // Título en la AppBar
             actions: const [
               Icon(Icons.search), // Ícono de búsqueda
               Icon(Icons.shopping_cart) // Ícono de carrito de compras
             ],
           ),
           drawer: const Drawer(), // Añade un Drawer al lado izquierdo
           body: const Center(
             child: Home(), // Añade el widget Home al cuerpo del Scaffold
           ),
           floatingActionButton: FloatingActionButton(
             onPressed: () {}, // Acción al presionar el botón
             child: const Icon(Icons.add), // Icono del botón
           ),
           bottomNavigationBar: BottomNavigationBar(
             items: const [
               BottomNavigationBarItem(
                 icon: Icon(Icons.home, color: Colors.purple), // Icono y color del item Home
                 label: "Home", // Etiqueta del item Home
               ),
               BottomNavigationBarItem(
                 icon: Icon(Icons.person, color: Colors.orange), // Icono y color del item Account
                 label: "Account", // Etiqueta del item Account
               )
             ],
           ),
         ),
       );
     }
   }
   ```

2. **Ejecuta la aplicación para ver los íconos en la AppBar**.

### Conclusión

Hemos construido gradualmente una aplicación Flutter que incluye una `AppBar` con íconos, un `Drawer`, un `FloatingActionButton`, un `BottomNavigationBar` y un widget `Home` que contiene un campo de texto y un botón para mostrar el texto ingresado.
