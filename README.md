<!-- PROFILE HEADER -->
<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=28&duration=2600&center=true&vCenter=true&width=900&lines=Hi%2C+I'm+Ali+Hassan;Flutter+%26+Firebase+Specialist;Android+%7C+iOS+%7C+Web+Engineer;I+build+clean%2C+scalable%2C+production-ready+apps" alt="Ali Hassan | Flutter & Firebase Specialist" />
</p>

<p align="center">
  <a href="https://github.com/devali3697">
    <img src="https://komarev.com/ghpvc/?username=devali3697&label=Profile%20Views&color=0e75b6&style=flat" alt="Profile views" />
  </a>
  <a href="mailto:devalihassan01@gmail.com">
    <img src="https://img.shields.io/badge/Email-devalihassan01%40gmail.com-D14836?logo=gmail&logoColor=white" alt="Email Ali" />
  </a>
  <a href="https://www.linkedin.com/in/ali-hassan-006aa2234">
    <img src="https://img.shields.io/badge/LinkedIn-ali--hassan--006aa2234-0A66C2?logo=linkedin&logoColor=white" alt="LinkedIn" />
  </a>
  <a href="https://www.upwork.com/freelancers/alihassanriaz?mp_source=share">
    <img src="https://img.shields.io/badge/Upwork-Portfolio-14a800?logo=upwork&logoColor=white" alt="Upwork Portfolio" />
  </a>
  <img src="https://img.shields.io/badge/Open%20for%20Work-✔-brightgreen" alt="Open for Work" />
  <img src="https://img.shields.io/github/followers/devali3697?style=social" alt="GitHub followers" />
  <img src="https://img.shields.io/github/stars/devali3697?style=social" alt="GitHub stars" />
</p>

---

## 👨‍💻 About Me
I turn ideas into **production-grade mobile & web apps** for startups and growing teams. With **Flutter + Firebase** as my core stack, I build apps that are **secure, scalable, and loved by users**.

- 📍 Based in Pakistan · 🌍 Working globally  
- 🛠 Expert in **Flutter, Firebase, Android (Java/Kotlin), Cloud Functions**  
- 💬 I love **Clean Architecture, Firebase scaling, Push/FCM, CI/CD**  
- 📂 Portfolio: <a href="https://www.upwork.com/freelancers/~018487c7c3f6c29f13?mp_source=share">Upwork Profile</a>

> **Currently:** Open to full-time/contract roles and MVP builds.

---

## 🧭 Expertise
- **Cross-Platform:** One Flutter codebase → Android, iOS, Web  
- **Firebase Backends:** RTDB, Firestore, Functions, Storage, Auth, Security Rules  
- **Performance & UX:** Offline patterns, smooth animations, A/B testing, analytics  
- **DevOps:** GitHub Actions, Fastlane, Play Store/App Store delivery, Crashlytics

---

## 🛠 Tech Stack
<p align="center">
  <img src="https://skillicons.dev/icons?i=flutter,dart,firebase,androidstudio,java,kotlin,git,github,postman,vscode,cloudflare" alt="Tech stack icons" />
</p>

**State:** GetX · Riverpod · Provider  
**Storage:** RTDB · Firestore · Storage  
**Other:** REST APIs · Theming · Clean Architecture · CI/CD  

---

## 🚀 Featured Highlights
- 🔹 **Multi-Branch Food & E-Commerce (Flutter + Firebase RTDB)**  
  Role-based CMS, dynamic branch menus, real-time orders, couponing & checkout
- 🔹 **Mining / Rewards Platform**  
  Hourly mining, referral tree, daily resets, boosted rewards with ads, fraud-safe
- 🔹 **Job Finder + Employer Portal**  
  Resume uploads, dashboards, moderation workflows, insights

> Want a demo? **Email me** or ping me on **LinkedIn**.

---

## 📦 Code Sample – Clean Architecture (Repository → UseCase → ViewModel → UI)
<details>
<summary><b>Show Dart snippet</b></summary>

```dart
// Example: Repository → UseCase → ViewModel → UI
// Notes: simple, testable, and UI-agnostic.

class AuthService {
  Future<User> login(String email, String password) async {
    // Call your API / Firebase Auth here
    throw UnimplementedError();
  }
}

class User {
  final String id;
  final String email;
  const User(this.id, this.email);
}

class AuthRepository {
  final AuthService api;
  AuthRepository(this.api);

  Future<User> login(String email, String password) => api.login(email, password);
}

class LoginUseCase {
  final AuthRepository repo;
  LoginUseCase(this.repo);

  Future<User> call(String email, String password) => repo.login(email, password);
}

class LoginViewModel extends ChangeNotifier {
  final LoginUseCase useCase;
  bool loading = false;
  String? error;
  User? current;

  LoginViewModel(this.useCase);

  Future<User?> login(String email, String password) async {
    loading = true;
    error = null;
    notifyListeners();
    try {
      final user = await useCase(email, password);
      current = user;
      return user;
    } catch (e) {
      error = e.toString();
      return null;
    } finally {
      loading = false;
      notifyListeners();
    }
  }
}
