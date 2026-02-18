<div align="center">

# 👋 Hey, I'm Jayprakash Pal

**Flutter Developer · Open Source Creator · Compiler Nerd**

*I build things that run everywhere — and tools that help others build better*

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/jayprakashpal1005/)
[![Portfolio](https://img.shields.io/badge/Portfolio-FF5722?style=for-the-badge&logo=google-chrome&logoColor=white)](https://jayprakashpal.web.app/)
[![FlutterJS](https://img.shields.io/badge/FlutterJS-02569B?style=for-the-badge&logo=flutter&logoColor=white)](https://flutterjs.dev/)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:jayprakash.pal888@gmail.com)

</div>

---

## About Me

I'm a Flutter developer from **Mumbai, India** with 4+ years of experience building cross-platform apps that real people use. I've shipped products to **10M+ users**, but what drives me most is solving the hard problems nobody else has tackled yet.

Right now that problem is **Flutter Web's broken SEO** — canvas rendering, bloated bundles, inaccessible output. So I built [FlutterJS](https://flutterjs.dev), a Dart-to-JavaScript compiler that outputs real HTML. It's early, rough around the edges, and I'm building it in the open because I think the direction matters.

- 🔭 Day job: **Mobile Developer at Idealake**, consulting for **ICICI Lombard**
- 🛠️ Nights & weekends: Building the **FlutterJS ecosystem** — compiler, SEO, server framework, testing
- 📍 Mumbai, India

---

## 🔨 The FlutterJS Ecosystem

> *Flutter Web outputs a canvas blob. Google can't index it. Screen readers can't parse it. Bundles are 2–5 MB. I got tired of working around this.*

FlutterJS compiles Dart/Flutter to real, semantic HTML+CSS+JS — dropping bundle sizes to **50–100 KB** and unlocking proper SEO. It's early-stage and not production-ready, but the core is working.

---

### [`flutterjs`](https://flutterjs.dev) — The Compiler

The core engine. Multi-phase pipeline: AST parsing → IR generation → JavaScript transpilation.

**What works:** Layout widgets (Container, Row, Column, Stack), Material widgets (Scaffold, AppBar, ElevatedButton, TextField), forms, StatefulWidget + setState, real HTML output.

**What's missing:** Animations, advanced Material widgets, Cupertino, some complex layout edge cases. Honest note — this is pre-alpha. I'm sharing early because people have been asking for this for years and I want to know if the direction is right before sinking more time in.

**Next big piece:** Server-side rendering on Node.js — pre-rendered HTML for instant first paint and SEO that works without JavaScript.

[![Website](https://img.shields.io/badge/flutterjs.dev-Visit-blue?style=flat-square)](https://flutterjs.dev)
[![GitHub](https://img.shields.io/badge/GitHub-Source-black?style=flat-square&logo=github)](https://github.com/flutterjsdev/flutterjs)

---

### [`flutterjs_server`](https://pub.dev/packages/flutterjs_server) — Write Dart APIs, Run on Node.js

Write HTTP servers in Dart. Compile them to JavaScript. Deploy anywhere Node.js runs.

```dart
@Server(port: 3000)
class MyApi {
  @Get('/hello')
  Response hello() => Response.ok({'message': 'Hello from Dart!'});

  @Post('/users')
  Response createUser(@Body() Map<String, dynamic> body) {
    final name = body['name'] as String?;
    if (name == null) return Response.badRequest({'error': 'name required'});
    return Response.created({'id': '1', 'name': name});
  }
}
```

Familiar annotations (`@Get`, `@Post`, `@Param`, `@Body`), built-in middleware (CORS, logger, bearer auth), and proof that the FlutterJS compiler works end-to-end for real server use cases.

[![pub.dev](https://img.shields.io/pub/v/flutterjs_server?style=flat-square&logo=dart)](https://pub.dev/packages/flutterjs_server)

---

### [`flutterjs_seo`](https://pub.dev/packages/flutterjs_seo) — SEO Metadata for FlutterJS Apps

Lightweight metadata injection built specifically for FlutterJS web apps. Because the whole point of compiling to real HTML is being able to actually use it — and that means proper meta tags, Open Graph, and indexable content.

[![pub.dev](https://img.shields.io/pub/v/flutterjs_seo?style=flat-square&logo=dart)](https://pub.dev/packages/flutterjs_seo)
[![Downloads](https://img.shields.io/badge/downloads-127-brightgreen?style=flat-square)](https://pub.dev/packages/flutterjs_seo)

---

### [`flutter_test_pilot`](https://pub.dev/packages/flutter_test_pilot) — Flutter Testing That Reads Like English

A fluent UI testing framework. Zero configuration — works without knowing your app's internal structure, routes, or state setup. Just add the dependency and start writing tests.

```dart
final loginSuite = TestSuite(
  name: 'User Login Flow',
  steps: [
    Type.hint('Email').text('user@example.com'),
    Type.hint('Password').text('password123'),
    Tap.text('Login'),
    Api.post(
      id: 'login-api',
      urlPattern: r'/api/auth/login',
      expectedStatus: 200,
      responseChecks: [ResponseCheck('token', exists())],
    ),
  ],
);
```

17+ widget-finding strategies, API interception + validation, parallel execution, retry logic, rich console & JSON reporting. Works with any architecture — BLoC, Provider, GetX, Riverpod.

[![pub.dev](https://img.shields.io/pub/v/flutter_test_pilot?style=flat-square&logo=dart)](https://pub.dev/packages/flutter_test_pilot)

---

### [`dead_code_analyzer`](https://pub.dev/packages/dead_code_analyzer) — Cut the Dead Weight

CLI plugin that finds unused code in Flutter/Dart projects. Custom exclusion patterns, monorepo support, CI/CD integration. Hit **500+ downloads in the first 15 days**.

[![pub.dev](https://img.shields.io/pub/v/dead_code_analyzer?style=flat-square&logo=dart)](https://pub.dev/packages/dead_code_analyzer)
[![Downloads](https://img.shields.io/badge/downloads-500+-brightgreen?style=flat-square)](https://pub.dev/packages/dead_code_analyzer)

---

## 💼 Production Work

| App | Scale | What I built |
|---|---|---|
| **ILTakeCare** (ICICI Lombard) | 10M+ downloads | Flutter UI, Bloc, Clean Architecture, REST APIs |
| **Axis Neo** (Axis Bank) | Transaction banking platform | Flutter across Android, iOS & Web |
| **Ripple** (Internal social platform) | Company-wide at Idealake | Flutter, Firebase, AES encryption |
| **ImmunOmate** | 1,000+ downloads | Led full end-to-end development |

---

## 🧰 Tech Stack

```
Mobile & Web     →  Flutter · Dart · FlutterFlow
State Mgmt       →  Bloc · Provider · GetX · Riverpod
Architecture     →  Clean Architecture · MVVM · MVC
Backend & APIs   →  Firebase · REST · Node.js · Express.js · WebSocket
Compiler / Tools →  AST parsing · IR generation · Dart CLI · static analysis
Databases        →  Firestore · SQLite · Hive · SharedPreferences
DevOps           →  Firebase Analytics · Crashlytics · CI/CD · Play Store · App Store
```

---

## 📈 GitHub Stats

<div align="center">

<!-- GitHub Stats — powered by github-stats-level.vercel.app (reliable alternative) -->
<img src="https://github-profile-summary-cards.vercel.app/api/cards/profile-details?username=jaypal1046&theme=tokyonight" width="100%" />

<img src="https://github-profile-summary-cards.vercel.app/api/cards/repos-per-language?username=jaypal1046&theme=tokyonight" width="49%" />
<img src="https://github-profile-summary-cards.vercel.app/api/cards/stats?username=jaypal1046&theme=tokyonight" width="49%" />

<!-- FlutterJS Repo Star Card -->
<br/><br/>

⭐ **If FlutterJS has helped you, starring the repo helps others find it**

[![FlutterJS](https://img.shields.io/github/stars/flutterjsdev/flutterjs?style=for-the-badge&logo=github&label=flutterjsdev%2Fflutterjs&color=02569B)](https://github.com/flutterjsdev/flutterjs)
[![Forks](https://img.shields.io/github/forks/flutterjsdev/flutterjs?style=for-the-badge&logo=github&color=02569B)](https://github.com/flutterjsdev/flutterjs/fork)

</div>

---

## 🎓 Education

**B.Sc. Information Technology** — Nagindas Khandwala College, Mumbai *(2018–2021)*

---

<div align="center">

**If FlutterJS sounds useful — try it, break it, and tell me what's wrong.** That's exactly what I need. 🚀

</div>
