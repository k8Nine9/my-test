<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Test Loader</title>

<style>
* {
  box-sizing: border-box;
}

body {
  margin: 0;
  height: 100vh;
  background: #0b0b0b;
  color: white;
  font-family: Arial, sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
}

.container {
  width: 90%;
  max-width: 400px;
  text-align: center;
}

h1 {
  font-size: 28px;
  margin-bottom: 10px;
}

p {
  color: #888;
}

.loader {
  width: 50px;
  height: 50px;
  border: 5px solid #333;
  border-top: 5px solid white;
  border-radius: 50%;
  animation: spin 1s linear infinite;
  margin: 30px auto;
}

button {
  width: 100%;
  padding: 14px;
  margin-top: 15px;
  border: 0;
  border-radius: 8px;
  background: white;
  color: black;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
}

button:hover {
  opacity: 0.85;
}

#login {
  display: none;
}

input {
  width: 100%;
  padding: 14px;
  margin-top: 10px;
  border: 1px solid #444;
  border-radius: 8px;
  background: #181818;
  color: white;
  font-size: 15px;
}

#result {
  margin-top: 15px;
  color: #aaa;
}
</style>
</head>

<body>

<div class="container">

  <div id="loaderScreen">
    <h1>TEST LOADER</h1>
    <p>준비 중...</p>

    <div class="loader"></div>

    <button onclick="startTest()">
      START
    </button>
  </div>


  <div id="login">
    <h1>LOGIN TEST</h1>
    <p>로컬 테스트용 로그인 화면</p>

    <input id="username" type="text" placeholder="Username">
    <input id="password" type="password" placeholder="Password">

    <button onclick="login()">
      LOGIN
    </button>

    <div id="result"></div>
  </div>

</div>


<script>

function startTest() {

  document.getElementById("loaderScreen").style.display = "none";

  document.getElementById("login").style.display = "block";
}


function login() {

  const username =
    document.getElementById("username").value;

  const password =
    document.getElementById("password").value;

  const result =
    document.getElementById("result");


  // 테스트용 값
  const correctUsername = "test";
  const correctPassword = "1234";


  if (
    username === correctUsername &&
    password === correctPassword
  ) {

    result.textContent = "로그인 성공";

  } else {

    result.textContent = "로그인 실패";

  }

}

</script>

</body>
</html>
