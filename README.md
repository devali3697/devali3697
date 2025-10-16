<p align="center">
  <img src="https://readme-typing-svg.herokuapp.com?size=26&duration=2800&center=true&vCenter=true&width=740&lines=Hi%2C+I'm+Ali+Hassan;Flutter+%26+Firebase+Specialist;Android+%7C+iOS+%7C+Web+Engineer;Building+Clean%2C+Scalable+%26+Production-Ready+Apps" alt="Ali Hassan | Flutter & Firebase Specialist" />
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

### 👨‍💻 About Me
I turn ideas into **production-grade mobile & web apps** for startups and growing teams.  
With **Flutter + Firebase** as my core stack, I build apps that are **secure, scalable, and loved by users**.

- 📍 Based in Pakistan | 🌍 Working globally  
- 🛠 Expert in **Flutter, Firebase, Android (Java/Kotlin), Cloud Functions**  
- 💬 Topics I love: **Clean Architecture, Firebase scaling, Push/FCM, CI/CD pipelines**  
- 📂 Full portfolio: <a href="https://www.upwork.com/freelancers/~018487c7c3f6c29f13?mp_source=share">Upwork Profile</a>

---

### 🧭 My Expertise
- **Cross-Platform Apps:** One Flutter codebase → Android, iOS, Web  
- **Robust Firebase Backends:** RTDB, Firestore, Functions, Storage, Auth, Security Rules  
- **Performance & UX:** Optimized builds, offline patterns, buttery animations  
- **DevOps:** GitHub Actions, CI/CD, App Store/Play Store deployment, analytics, crash reporting  

---

### 🛠 Tech Stack
<p align="center">
  <img src="https://skillicons.dev/icons?i=flutter,dart,firebase,androidstudio,java,kotlin,git,github,postman,vscode,cloudflare" alt="Tech stack icons" />
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

<!--
Why these params?
- cache_seconds keeps cards fresh enough without hitting rate limits
- hide_border + theme for clean look
- card_width/height to avoid layout jumps
- Top Langs: hide markup (html, css) noise; Dart weight fixed via .gitattributes
-->

<p align="center">
  <img height="160" 
       src="https://github-readme-stats.vercel.app/api?username=devali3697&show_icons=true&theme=tokyonight&hide_border=true&include_all_commits=true&count_private=true&cache_seconds=21600&v=3" 
       alt="GitHub stats" />
  <img height="160" 
       src="https://github-readme-stats.vercel.app/api/top-langs/?username=devali3697&layout=compact&hide_border=true&theme=tokyonight&langs_count=8&hide=html,css&card_width=420&cache_seconds=21600&v=3" 
       alt="Top languages" />
</p>

<p align="center">
  <img height="170"
    src="https://streak-stats.demolab.com?user=devali3697&theme=tokyonight&hide_border=true&date_format=j%20M%5B%20Y%5D&card_width=500&cache=21600&v=3"
    alt="GitHub Streak" />
</p>

<p align="center">
  <a href="https://github.com/ryo-ma/github-profile-trophy">
    <img src="https://github-profile-trophy.vercel.app/?username=devali3697&margin-w=6&no-frame=true&theme=flat&row=1&column=7&cache=21600&v=3" 
         alt="GitHub Trophies" />
  </a>
</p>

<p align="center">
  <img 
    src="https://github-readme-activity-graph.vercel.app/graph?username=devali3697&theme=tokyo-night&hide_border=true&radius=8&area=true&custom_title=Contribution%20Activity&v=3" 
    alt="Contribution Activity Graph" />
</p>

---

### 🧩 Code Sample (Mini Snippet)
<details>
<summary><b>📦 Clean Architecture in Flutter (Repository → UseCase → ViewModel → UI)</b></summary>

```dart
// Example: Repository → UseCase → ViewModel → UI

class AuthService {
  Future<User> login(String email, String password) async {
    // call your API / Firebase Auth here
    // return a User instance
    throw UnimplementedError();
  }
}

class User {
  final String id;
  final String email;
  User(this.id, this.email);
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
    loading = true; error = null; notifyListeners();
    try {
      final user = await useCase(email, password);
      current = user;
      return user;
    } catch (e) {
      error = e.toString();
      return null;
    } finally {
      loading = false; notifyListeners();
    }
  }
}
