---
title: "Mostrar imágenes desde internet"
prev:
  title: Implementar Swipe para cancelar
  path: /docs/cookbook/gestures/dismissible
next:
  title: Efecto 'Fade in' en imágenes con un placeholder
  path: /docs/cookbook/images/fading-in-images
---

Mostrar imágenes es fundamental para la mayoría de las aplicaciones móviles. Flutter proporciona el 
widget de [`Image`]({{site.api}}/flutter/widgets/Image-class.html) para mostrar 
diferentes tipos de imágenes.

Para trabajar con imágenes desde una URL, 
usa el constructor 
[`Image.network`]({{site.api}}/flutter/widgets/Image/Image.network.html).

<!-- skip -->
```dart
Image.network(
  'https://picsum.photos/250?image=9',
)
```

## Bono: Gifs animados

Una cosa increíble sobre el widget `Image` : ¡también es compatible con los gifs animados 
listos para usar!

<!-- skip -->
```dart
Image.network(
  'https://github.com/flutter/plugins/raw/master/src/packages/video_player/doc/demo_ipod.gif?raw=true',
);
```

## Placeholders y caché

El constructor predeterminado de `Image.network` no maneja una funcionalidad más avanzada, como el 
desvanecimiento de imágenes después de cargarlas o el almacenamiento en caché de las imágenes en el 
dispositivo una vez que se han descargado. Para lograr estas tareas, por favor consulte las 
siguientes recetas:

  * [Efecto “Fade in” en imágenes con un placeholder](docs/cookbook/images/fading-in-images/)
  * [Trabajando con imágenes en caché](/docs/cookbook/images/cached-images/) 

## Ejemplo completo

```dart
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    var title = 'Web Images';

    return MaterialApp(
      title: title,
      home: Scaffold(
        appBar: AppBar(
          title: Text(title),
        ),
        body: Image.network(
          'https://picsum.photos/250?image=9',
        ),
      ),
    );
  }
}
```

![Network Image Demo](/images/cookbook/network-image.png){:.site-mobile-screenshot}
