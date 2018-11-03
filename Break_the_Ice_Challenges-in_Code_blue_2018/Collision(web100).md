# ▼▼▼Collision(Web:100)▼▼▼

```
GET /? HTTP/1.1
Host: web2.sl7ctf.cf
```

↓

```
HTTP/1.1 200 OK
Date: Thu, 01 Nov 2018 05:51:08 GMT
Server: Apache/2.4.10 (Debian)
Vary: Accept-Encoding
Content-Length: 2883
Connection: close
Content-Type: text/html; charset=UTF-8

<script>alert("Input your username and password to get ACCESS!")</script>
<!DOCTYPE html>
<html>
<head>
	<title>Stellar collision</title>
	<style type="text/css">
		@import url(https://fonts.googleapis.com/css?family=Roboto:300);

.login-page {
  width: 360px;
  padding: 8% 0 0;
  margin: auto;
}
.form {
  position: relative;
  z-index: 1;
  background: #FFFFFF;
  max-width: 360px;
  margin: 0 auto 100px;
  padding: 45px;
  text-align: center;
  box-shadow: 0 0 20px 0 rgba(0, 0, 0, 0.2), 0 5px 5px 0 rgba(0, 0, 0, 0.24);
}
.form input {
  font-family: "Roboto", sans-serif;
  outline: 0;
  background: #f2f2f2;
  width: 100%;
  border: 0;
  margin: 0 0 15px;
  padding: 15px;
  box-sizing: border-box;
  font-size: 14px;
}
.form button {
  font-family: "Roboto", sans-serif;
  text-transform: uppercase;
  outline: 0;
  background: #4CAF50;
  width: 100%;
  border: 0;
  padding: 15px;
  color: #FFFFFF;
  font-size: 14px;
  -webkit-transition: all 0.3 ease;
  transition: all 0.3 ease;
  cursor: pointer;
}
.form button:hover,.form button:active,.form button:focus {
  background: #43A047;
}
.form .message {
  margin: 15px 0 0;
  color: #b3b3b3;
  font-size: 12px;
}
.form .message a {
  color: #4CAF50;
  text-decoration: none;
}
.form .register-form {
  display: none;
}
.container {
  position: relative;
  z-index: 1;
  max-width: 300px;
  margin: 0 auto;
}
.container:before, .container:after {
  content: "";
  display: block;
  clear: both;
}
.container .info {
  margin: 50px auto;
  text-align: center;
}
.container .info h1 {
  margin: 0 0 15px;
  padding: 0;
  font-size: 36px;
  font-weight: 300;
  color: #1a1a1a;
}
.container .info span {
  color: #4d4d4d;
  font-size: 12px;
}
.container .info span a {
  color: #000000;
  text-decoration: none;
}
.container .info span .fa {
  color: #EF3B3A;
}
body {
  background: #76b852; /* fallback for old browsers */
  background: -webkit-linear-gradient(right, #76b852, #8DC26F);
  background: -moz-linear-gradient(right, #76b852, #8DC26F);
  background: -o-linear-gradient(right, #76b852, #8DC26F);
  background: linear-gradient(to left, #76b852, #8DC26F);
  font-family: "Roboto", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;      
}
	</style>
	<script type="text/javascript">
		$('.message a').click(function(){
   $('form').animate({height: "toggle", opacity: "toggle"}, "slow");
});
	</script>
</head>
<body>
<div class="login-page">
  <div class="form">
    <form class="login-form">
      <input type="text" placeholder="username"/>
      <input type="password" placeholder="password"/>
      <button>login</button>
    </form>
  </div>
</div>
</body>
</html>
























































































































<!--
	Hint : 
		if((md5($username) === md5($password)) && ($username != $password))
-->
```

↓

Collision problem with md5

---

I could find conflicting values by google search

↓

```
POST / HTTP/1.1
Host: web2.sl7ctf.cf
Content-Type: application/x-www-form-urlencoded
Content-Length: 787

username=%d1%31%dd%02%c5%e6%ee%c4%69%3d%9a%06%98%af%f9%5c%2f%ca%b5%87%12%46%7e%ab%40%04%58%3e%b8%fb%7f%89%55%ad%34%06%09%f4%b3%02%83%e4%88%83%25%71%41%5a%08%51%25%e8%f7%cd%c9%9f%d9%1d%bd%f2%80%37%3c%5b%d8%82%3e%31%56%34%8f%5b%ae%6d%ac%d4%36%c9%19%c6%dd%53%e2%b4%87%da%03%fd%02%39%63%06%d2%48%cd%a0%e9%9f%33%42%0f%57%7e%e8%ce%54%b6%70%80%a8%0d%1e%c6%98%21%bc%b6%a8%83%93%96%f9%65%2b%6f%f7%2a%70&password=%d1%31%dd%02%c5%e6%ee%c4%69%3d%9a%06%98%af%f9%5c%2f%ca%b5%07%12%46%7e%ab%40%04%58%3e%b8%fb%7f%89%55%ad%34%06%09%f4%b3%02%83%e4%88%83%25%f1%41%5a%08%51%25%e8%f7%cd%c9%9f%d9%1d%bd%72%80%37%3c%5b%d8%82%3e%31%56%34%8f%5b%ae%6d%ac%d4%36%c9%19%c6%dd%53%e2%34%87%da%03%fd%02%39%63%06%d2%48%cd%a0%e9%9f%33%42%0f%57%7e%e8%ce%54%b6%70%80%28%0d%1e%c6%98%21%bc%b6%a8%83%93%96%f9%65%ab%6f%f7%2a%70
```

↓

```
HTTP/1.1 200 OK
Date: Thu, 01 Nov 2018 06:15:29 GMT
Server: Apache/2.4.10 (Debian)
Vary: Accept-Encoding
Content-Length: 2841
Connection: close
Content-Type: text/html; charset=UTF-8

SL7{Gr3at_buddY_c0llision_DoNE}
～Below, omitted～
```

↓

`SL7{Gr3at_buddY_c0llision_DoNE}`
