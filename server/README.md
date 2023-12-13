A server app built using [Shelf](https://pub.dev/packages/shelf),
configured to enable running with [Docker](https://www.docker.com/).

This sample code handles HTTP GET requests to `/` and `/echo/<message>`

# Running the sample

## Running with the Dart SDK

reference: https://blog.codemagic.io/writing-your-backend-in-dart/


Create empty flutter project then run in terminal:
dart create --template=server-shelf server

And the result will be as follows:
├── .dart_tool
├── bin
│    └── server.dart
├── test
│    └── server_test.dart
├── .dockerignore
├── .gitignore
├── analysis_options.yaml
├── CHANGELOG.md
├── Dockerfile
├── pubspec.lock
├── pubspec.yaml
└── README.md


To run project :
cd server
dart bin/server.dart
We’ll see that our server will successfully be listening to requests in port 8080.
open safari type localhost:8080
output will be : Hello, World!


or from a second terminal:
$ curl http://0.0.0.0:8080
Hello, World!
$ curl http://0.0.0.0:8080/echo/I_love_Dart
I_love_Dart
$ curl http://0.0.0.0:8080/todos
[{"id":"1","name":"First Todo"}]%

Note: close and restart server after any change to make that change visible



You can run the example with the [Dart SDK](https://dart.dev/get-dart)
like this:

```
$ dart run bin/server.dart
Server listening on port 8080
```

And then from a second terminal:
```
$ curl http://0.0.0.0:8080
Hello, World!
$ curl http://0.0.0.0:8080/echo/I_love_Dart
I_love_Dart
```

## Running with Docker

If you have [Docker Desktop](https://www.docker.com/get-started) installed, you
can build and run with the `docker` command:

```
$ docker build . -t myserver
$ docker run -it -p 8080:8080 myserver
Server listening on port 8080
```

And then from a second terminal:
```
$ curl http://0.0.0.0:8080
Hello, World!
$ curl http://0.0.0.0:8080/echo/I_love_Dart
I_love_Dart
```

You should see the logging printed in the first terminal:
```
2021-05-06T15:47:04.620417  0:00:00.000158 GET     [200] /
2021-05-06T15:47:08.392928  0:00:00.001216 GET     [200] /echo/I_love_Dart
```
