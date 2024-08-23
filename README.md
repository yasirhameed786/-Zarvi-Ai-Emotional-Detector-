# -Zarvi-Ai-Emotional-Detector-
It is an AI tool to detect the human sentiment by their tweet


<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<link rel="stylesheet" href="https://stackpath.bootstrapcdn.com/bootstrap/4.3.1/css/bootstrap.min.css" integrity="sha384- ggOyR0iXCbMQv3Xipma34MD+dH/1fQ784/j6cY/iJTQUOhcWr7x9JvoRxT2MZw1T" crossorigin="anonymous">
<script src="app.js"></script>
<title>To Do List</title>
</head>
<body>
<header class="bg-success text-white p-5">
<div class="container">
<div class="row">
<div class="col-lg-12 col-md-12 col-sm-12">
<font face="Comic sans MS" size="11" color="black">
<strong>ToDo List</strong>
</font>
</div>
</div>
</div>
</header>
<div class="container mt-3">
<h2>Add Items</h2>
<label id="lblsuccess" class="text-success" style="display: none;">
</label>
<form id="addForm">
<div class="row">
<div class="col-lg-7 col-md-7 col-sm-7">
<input type="text" onkeyup="toggleButton(this, 'submit')" class="form-control" id="item">
</div>
<div class="col-lg-5 col-md-5 col-sm-5">
<input type="submit" class="btn btn-dark" id="submit" value="Submit" disabled>
</div>
</div>
</form>
<h3 class="mt-4">Tasks</h3>
<form id="addForm">
<ul class="list-group" id="items"></ul>
</form>
</div>
</body>
</html>
<script> window.onload = () =>
{
const form1 = document.querySelector("#addForm"); let items = document.getElementById("items");
let submit = document.getElementById("submit"); let editItem = null; form1.addEventListener("submit", addItem); items.addEventListener("click", removeItem);
};
function addItem(e)
{
e.preventDefault();
if (submit.value != "Submit")
{
console.log("Hello");
editItem.target.parentNode.childNodes[0].data
= document.getElementById("item").value; submit.value = "Submit";

document.getElementById("item").value = ""; document.getElementById("lblsuccess").innerHTML
= "Text edited successfully";
document.getElementById("lblsuccess")
.style.display = "block"; setTimeout(function()
{
document.getElementById("lblsuccess")
.style.display = "none";
}, 3000);
return false;
}
let newItem = document.getElementById("item").value; if (newItem.trim() == "" || newItem.trim() == null) return false;
else
document.getElementById("item").value = ""; let li = document.createElement("li"); li.className = "list-group-item";
let deleteButton = document.createElement("button");
deleteButton.className =
"btn-danger btn btn-sm float-right delete"; deleteButton.appendChild(document.createTextNode("Delete")); let editButton = document.createElement("button"); editButton.className =
"btn-success btn btn-sm float-right edit"; editButton.appendChild(document.createTextNode("Edit")); li.appendChild(document.createTextNode(newItem)); li.appendChild(deleteButton);
li.appendChild(editButton); items.appendChild(li);
}
function removeItem(e)
{
e.preventDefault();
if (e.target.classList.contains("delete"))
{
if (confirm("Are you Sure?"))
{
let li = e.target.parentNode; items.removeChild(li);
document.getElementById("lblsuccess").innerHTML
= "Text deleted successfully"; document.getElementById("lblsuccess")
.style.display = "block"; setTimeout(function()
{
document.getElementById("lblsuccess")
.style.display = "none";
}, 3000);
}
}
if (e.target.classList.contains("edit"))
{
document.getElementById("item").value = e.target.parentNode.childNodes[0].data; submit.value = "EDIT";
editItem = e;
}
}
function toggleButton(ref, btnID)
{
document.getElementById(btnID).disabled = false;
}
</script>

3.
EX.NO.03	Create a simple micro blogging application (like twitter) that allows people to post their content which can be viewed by people who follow them using HTML

AIM:
To Create a simple micro blogging application (like twitter) that allows people to post their content which can be viewed by people who follow them using HTML

ALGORITHM:
Step 1: Set up the basic HTML structure:
Create a new HTML file and set up the basic structure with the `<html>`, `<head>`, and
`<body>` tags.
Include a `<title>` element to give your page a title.
Step 2: Design the header section
Inside the `<body>` tag, create a header section that contains the title of your microblogging application and any other navigation elements you want to add.
Step 3: Create a section for posting content:
Add a text area and a "Post" button to allow users to enter their content and submit it to the microblog.
You can use the `<form>` element
To wrap these elements and use the `<textarea>` and `<input>` tags for the text area and button, respectively.
Step 4: Implement the posting functionality
Using JavaScript or a server-side language, handle the form submission and save the content of the post to a database or an array (if you are using client-side storage).
Ensure that each post has a unique identifier and includes the content, author information, and timestamp.
Step 5: Display the user's posts
Create a section to display the user's posts.
You can use a `<div>` element for each post and fill it with the post content, author details, and timestamp.
Use CSS to style the posts and make them visually appealing.
Step 6:Implement the follow functionality:
Add a button or link for users to follow other users. This functionality can be implemented using JavaScript To toggle the follow status for a user.
You can store the list of followers for each user in a database or use local storage.
Step 7:Display followed users' posts:
Create a section to display the posts from the users that the current user is following.
Retrieve the posts from the database or array and display them in the same format as the user's posts.
Step 8: Add additional features (optional):
You	can enhance the microblogging application by adding features like	liking, commenting, retweeting, hashtags, user profiles, etc.
Each of these features will require additional HTML elements, CSS, and JavaScript to implement.
Step 9: Implement user authentication (optional)
If you want users to have accounts and be able to log in, you'll need to implement user authentication.
This step involves user registration, login, and managing user sessions to ensure that users can access their accounts and post content securely.
Step 10:Test the application thoroughly:
Finally, thoroughly test the microblogging application
To ensure it works as expected, handles errors gracefully, and provides a smooth user experience.
Note:
While the above algorithm outlines the basic steps for creating a microblogging application using HTML.
It’s essential to consider security measures, database integration, and user experience to make a complete and robust application.
For a production-level application, you might need to use server-side technologies, databases, and frameworks to handle the backend logic and scalability effectively.
CODING:
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Simple Microblogging App</title>
<style> body
{
font-family: Arial, sans-serif; margin: 0;
padding: 0;
}
Header
{
background-color: #333; color: #fff;
padding: 10px; text-align: center;
}
#timeline
{
margin: 10px;
}
footer
{
background-color: #f0f0f0; padding: 10px;
position: fixed; bottom: 0;
left: 0;
width: 100%;
}
#postContent
{
width: 100%; resize: vertical; min-height: 100px;
}
button
{
margin-top: 5px;
}
#loginForm, #signupForm
{
max-width: 300px; margin: 0 auto; padding: 20px;
border: 1px solid #ccc; border-radius: 5px; margin-top: 50px;
}
#loginForm h2, #signupForm h2
{
text-align: center;
}
</style>
</head>
<body>
<div class="container">
<h1>Microblogging App</h1>
<form>
<textarea name="postContent" id="postContent" cols="30" rows="5" placeholder="Write your post..."></textarea>
<button type="button" onclick="postContent()">Post</button>
</form>
<div id="timeline">
<div class="post">
<p><strong>Username:</strong>
The user will be followed by user. But in order that you may see whence all this born error is of those who accuse pleasure and praise pain, I will open the whole matter.this post in for fun only not hating a person.
</p>
</div>
</div>
</div>
<script>
function postContent() {
}
</script>
</body>
</html>
<!DOCTYPE html>
<html>
<head>
<title>Login</title>
<link rel="stylesheet" href="{{ url_for('static', filename='styles.css') }}">
</head>
<body>
<div id="loginForm">
<h2>Login</h2>
<form action="/login" method="POST">
<input type="text" name="username" placeholder="Username" required>
<input type="password" name="password" placeholder="Password" required>
<button type="submit">Login</button>
</form>
<p>Don't have an account? <a href="/signup">Signup</a></p>
</div>
</body>
</html>
