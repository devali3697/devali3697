<!-- ====== PROFILE HEADER ====== -->
<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=26&duration=2800&center=true&vCenter=true&width=740&lines=Hi%2C+I'm+Ali+Hassan;Flutter+%26+Firebase+Developer;Android+%7C+iOS+%7C+Web+Engineer;I+build+clean%2C+scalable%2C+production-ready+apps" />
</p>

<p align="center">
  <a href="https://github.com/devali3697">
    <img src="https://komarev.com/ghpvc/?username=devali3697&label=Profile%20Views&color=0e75b6&style=flat" />
  </a>
  <a href="mailto:devalihassan01@gmail.com">
    <img src="https://img.shields.io/badge/Email-devalihassan01%40gmail.com-D14836?logo=gmail&logoColor=white" />
  </a>
  <a href="https://www.linkedin.com/in/ali-hassan-006aa2234">
    <img src="https://img.shields.io/badge/LinkedIn-ali--hassan--006aa2234-0A66C2?logo=linkedin&logoColor=white" />
  </a>
  <a href="https://www.upwork.com/freelancers/alihassanriaz?mp_source=share">
    <img src="https://img.shields.io/badge/Upwork-Portfolio-14a800?logo=upwork&logoColor=white" />
  </a>
  <img src="https://img.shields.io/badge/Open%20for%20Work-✔-brightgreen" />
  <img src="https://img.shields.io/github/followers/devali3697?style=social" />
  <img src="https://img.shields.io/github/stars/devali3697?style=social" />
</p>

---

### 👨‍💻 About Me
I help startups & teams turn ideas into **production-ready mobile & web apps**.  
With **clean architecture**, **scalable Firebase backends**, and **pixel-perfect UI**, I ship apps that are **fast, secure, and delightful**.

- 📍 Pakistan • 🛠 Flutter, Firebase, Android (Java/Kotlin), Cloud Functions  
- 💬 Ask me about: **State management, RTDB/Firestore design, FCM/Push, CI/CD, REST APIs**  
- 📂 **Full portfolio & live work:**  
  **Upwork:** https://www.upwork.com/freelancers/~018487c7c3f6c29f13?mp_source=share

---

### 🧭 What I Do
- **End-to-End App Development:** Android, iOS & Web with one Flutter codebase  
- **Scalable Firebase Backends:** RTDB/Firestore, Auth, Storage, Functions, security rules  
- **Performance & UX:** Smooth animations, cached images, offline patterns, lazy loading  
- **DevOps & Quality:** GitHub Actions, crash/reporting, analytics, app bundle signing

---

### 🛠 Tech Stack
<p align="center">
  <img src="https://skillicons.dev/icons?i=flutter,dart,firebase,androidstudio,java,kotlin,git,github,postman,vscode,cloudflare" />
</p>

- **State management:** Provider · GetX · Riverpod  
- **Backend & storage:** Realtime DB · Firestore · Cloud Functions · Storage  
- **Other:** REST/JSON · FCM · App theming · Clean Architecture · CI/CD (GHA)

---

### 🚀 Featured Highlights
- 🔹 **Multi-branch Food & E-commerce (Flutter + Firebase RTDB)** — dynamic categories/items per branch, roles, admin panel, push notifications, real-time orders
- 🔹 **Mining/Rewards App** — hour-based mining logic, daily resets, boosts via rewarded ads, referral tree, secure backend checks
- 🔹 **Job Finder + Employer Portal** — resume upload (Storage), employer dashboards, category search, analytics, moderation tools

> Want a quick walkthrough or sample code? **Email:** devalihassan01@gmail.com

---

### 🔥 Featured Projects (Quick View)
| Project | Stack | Highlights |
|---|---|---|
| **SCS Food (Multi-branch Ordering)** | Flutter · Firebase RTDB · Functions | Branch-wise menus, cart/checkout, order tracking, admin CMS |
| **C Coin Mining Network** | Flutter · RTDB · Storage · FCM | Real-time timers, boosts via ads, referral tree, daily resets |
| **Job Finder / Employer Portal** | Flutter · Storage · Firestore | Resume upload, role-based dashboards, listings & analytics |

<!-- Replace demo GIFs/links below with your actual repos or media if available -->
<p align="center">
  <!-- <img src="https://raw.githubusercontent.com/USER/REPO/main/demo.gif" width="520" /> -->
</p>

---

### 📊 GitHub Stats
<p align="center">
  <img height="160" src="https://github-readme-stats.vercel.app/api?username=devali3697&show_icons=true&theme=tokyonight&hide_border=true" />
  <img height="160" src="https://github-readme-stats.vercel.app/api/top-langs/?username=devali3697&layout=compact&hide_border=true&theme=tokyonight" />
</p>

<p align="center">
  <img height="170" src="https://github-readme-streak-stats.herokuapp.com?user=devali3697&theme=tokyonight&hide_border=true" />
</p>

<p align="center">
  <a href="https://github.com/ryo-ma/github-profile-trophy">
    <img src="https://github-profile-trophy.vercel.app/?username=devali3697&margin-w=6&no-frame=true&theme=flat&row=1&column=7" />
  </a>
</p>

<p align="center">
  <img src="https://github-readme-activity-graph.vercel.app/graph?username=devali3697&theme=tokyo-night&hide_border=true" />
</p>

---

### 🧩 Code Samples (Mini Snippets)

<details>
<summary><b>📦 Clean Architecture (Feature Slice)</b></summary>

```dart
// Example: Repository -> UseCase -> ViewModel -> UI (MVVM)
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

  LoginViewModel(this.useCase);

  Future<User?> login(String email, String password) async {
    loading = true; error = null; notifyListeners();
    try { final user = await useCase(email, password); return user; }
    catch (e) { error = e.toString(); return null; }
    finally { loading = false; notifyListeners(); }
  }
}
