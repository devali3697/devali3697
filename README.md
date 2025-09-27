<!-- ====== PROFILE HEADER ====== -->
<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=26&duration=2800&center=true&vCenter=true&width=740&lines=Hi%2C+I'm+Ali+Hassan;Flutter+%26+Firebase+Specialist;Android+%7C+iOS+%7C+Web+Engineer;Building+Clean%2C+Scalable+%26+Production-Ready+Apps" />
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
I turn ideas into **production-grade mobile & web apps** for startups and growing teams.  
With **Flutter + Firebase** as my core stack, I build apps that are **secure, scalable, and loved by users**.

- 📍 Based in Pakistan | 🌍 Working globally  
- 🛠 Expert in **Flutter, Firebase, Android (Java/Kotlin), Cloud Functions**  
- 💬 Topics I love: **Clean Architecture, Firebase scaling, Push/FCM, CI/CD pipelines**  
- 📂 Full portfolio: [Upwork Profile](https://www.upwork.com/freelancers/~018487c7c3f6c29f13?mp_source=share)

---

### 🧭 My Expertise
- **Cross-Platform Apps:** One Flutter codebase → Android, iOS, Web  
- **Robust Firebase Backends:** RTDB, Firestore, Functions, Storage, Auth, Security Rules  
- **Performance & UX:** Optimized builds, offline patterns, buttery animations  
- **DevOps:** GitHub Actions, CI/CD, App Store/Play Store deployment, analytics, crash reporting  

---

### 🛠 Tech Stack
<p align="center">
  <img src="https://skillicons.dev/icons?i=flutter,dart,firebase,androidstudio,java,kotlin,git,github,postman,vscode,cloudflare" />
</p>

- **State management:** GetX · Riverpod · Provider  
- **Backend & Storage:** RTDB · Firestore · Cloud Functions · Storage  
- **Other:** REST APIs · App theming · Clean Architecture · CI/CD  

---

### 🚀 Featured Highlights
- 🔹 **Multi-Branch Food & E-Commerce (Flutter + Firebase RTDB)**  
  → Dynamic branch-wise menus, checkout, real-time orders, role-based admin CMS  
- 🔹 **Mining/Rewards Platform**  
  → Secure hourly mining, referral tree, daily resets, boosts with rewarded ads  
- 🔹 **Job Finder + Employer Portal**  
  → Resume uploads, dashboards, category search, moderation tools, analytics  

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

### 🧩 Code Sample (Mini Snippet)
<details>
<summary><b>📦 Clean Architecture in Flutter</b></summary>

```dart
// Example: Repository → UseCase → ViewModel → UI
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
    try {
      final user = await useCase(email, password);
      return user;
    } catch (e) {
      error = e.toString();
      return null;
    } finally {
      loading = false; notifyListeners();
    }
  }
}
