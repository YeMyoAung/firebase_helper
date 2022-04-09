# Starlight Firebase Helper (Paid Package 500,00 MMK)

Starlight Firebase Helper is firebase helper package that specialize firestore.
If you hardly to watch your stored firestore data with real-time,
this package will save your days.

## Highlight Features

| Name      | Method              | type         |
| --------- | ------------------- | ------------ |
| Firestore | chunkStreamRegister | void         |
| Firestore | unset               | void         |
| Firestore | unsetAll            | void         |
| Firestore | stream              | Stream       |
| Firestore | isolateStream       | Stream       |
| Firestore | next                | Future<void> |

## Upcoming Features

| Name              | Method                                        | type   |
| ----------------- | --------------------------------------------- | ------ |
| FirebaseAuth      | phone auth with pop-up pin code ui            | Future |
| FirebaseMessaging | firebase messaging with built-in notification | Future |

## Preview

For More Info,you can purchase this package

## Installation

Add starlight_firebase_helper as dependency to your pubspec file.

```dart
   starlight_firebase_helper:
    git:
      url: git@github.com:YeMyoAung/starlight_firebase_helper.git
```

## Setup

No additional integration steps are required for Android and Ios.

## Usage

First of all you need to import our package.

```dart
import 'package:starlight_firebase_helper/starlight_firebase_helper.dart';
```

And then you can use easily.

## Important Note

If you want to use `Highlight Features`,you need to register with unique ID on `chunkStreamRegister`.

## Register

You can register a chunk stream by passing `id`,`path`,`orderBy`,`chunk` and `descending`.
`id` must be a unique string,`path` must be your firestore path,`orderBy` must be a string,
`chunk` must be a numeric and `descending` is an optional parameter default with true.

```dart
   StarlightFirestore.chunkStreamRegister(
             id: 'userTable',
             path: 'userTable',
             orderBy: 'createdAt',
             chunk: 1000,
             descending: true,
  );
```

## Dispose

You can dispose your chunk stream by using `unset` method with registered ID.

```dart
    StarlightFirestore.unset('userTable');
```

## Dispose All

You can dispose all of your chunk stream by using `unsetAll` method.
you can't execute that process anymore.

```dart
   StarlightFirestore.unsetAll();
```

## Stream

If you want to `sort`,`unique` and watch stored firebase data,you can you
`stream` method by passing `id`(registered ID), `filter`

```dart
    StarlightFirestore.stream(
             'userTable',
             (dynamic event) => StarlightIsolateModel(
               allUsers.map((user) => user.toJson()).toList(),
               event.docs as List,
               (dynamic p0, dynamic p1, [index = 0]) => p0['id'] == p1['id'],
               (dynamic previous, dynamic current) =>
                   (previous['createdAt']).compareTo(current['createdAt']),
             ),
           ).listen((event) async {
             ///ToDo
          }
   });
```

## Isolate Stream

If you want to `sort`,`unique` and watch stored firebase data with isolate,you can you
`isolateStream` method by passing `id`(registered ID), `filter`

```dart
    StarlightFirestore.isolateStream(
             'userTable',
             (dynamic event) => StarlightIsolateModel(
               allUsers.map((user) => user.toJson()).toList(),
               event.docs as List,
               (dynamic p0, dynamic p1, [index = 0]) => p0['id'] == p1['id'],
               (dynamic previous, dynamic current) =>
                   (previous['createdAt']).compareTo(current['createdAt']),
             ),
           ).listen((event) async {
             ///ToDo
          }
   });
```

## next

You can refresh your stream by using `next` method by passing `id`,`path`,`orderBy`,`chunk` and `descending`.
`id` must be a unique string,`path` must be your firestore path,`orderBy` must be a string,
`chunk` must be a numeric and `descending` is an optional parameter default with true.

```dart
    StarlightFirestore.next(
        id: itemTable,
        path: itemTable,
        orderBy: 'point',
        chunk: 100,
        descending: true,
    );
```

## Contact Us

[Starlight Studio](https://www.facebook.com/starlightstudio.of/)
