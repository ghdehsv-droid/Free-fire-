<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<title>Login | Premium</title>
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<!-- Tailwind -->
<script src="https://cdn.tailwindcss.com"></script>

<!-- Firebase -->
<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-app-compat.js"></script>
<script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-auth-compat.js"></script>

<style>
body{
  background:url('https://images.unsplash.com/photo-1501785888041-af3ef285b470') center/cover no-repeat;
}
.glass{
  backdrop-filter: blur(15px);
  background: rgba(255,255,255,0.15);
}
</style>
</head>

<body class="min-h-screen flex items-center justify-center">

<div class="glass w-[90%] max-w-md rounded-2xl p-6 shadow-2xl text-white">
  <h2 class="text-2xl font-bold text-center mb-6">🔥 Premium Login</h2>

  <input id="email" type="email" placeholder="Email"
    class="w-full bg-transparent border-b mb-4 outline-none p-2">

  <input id="password" type="password" placeholder="Password"
    class="w-full bg-transparent border-b mb-4 outline-none p-2">

  <button onclick="loginUser()"
    class="w-full bg-green-900 hover:bg-green-800 py-2 rounded-xl">
    Login
  </button>

  <p class="text-center mt-4 text-sm">
    Don’t have an account?
    <a href="register.html" class="underline">sign up</a>
  </p>
</div>

<script>
const firebaseConfig = {
    apiKey "AIzaSyCtdfB7eOwCV3Or39hbRkIiUQFmV3oXOSk",
  authDomain: "free-d0cd4.firebaseapp.com",
  databaseURL: "http://free-d0cd4.firebasestorage.com",
  projectId: "free-d0cd4"
};

firebase.initializeApp(firebaseConfig);

const auth = firebase.auth();
const db = firebase.database();

// 🤖 Telegram
const BOT_TOKEN = "@aloneboy_bot";
const CHAT_ID = "-@ALONE_BOU";

firebase.initializeApp(firebaseConfig);

function loginUser(){
  const email = email.value;
  const password = document.getElementById("password").value;

  firebase.auth().signInWithEmailAndPassword(email,password)
  .then(()=>{
    alert("Login Successful");
    // redirect to paid page
    window.location.href="dashboard.html";
  })
  .catch(err=>alert(err.message));
}
</script>

</body>
</html>
