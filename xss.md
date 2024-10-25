# Cookies and Cross-scripting

Liam Keane

### Part 1: Cookies

1. There is a Name-value pair of Theme-Blue.

2. The value changed to Red.

3. The GET header specifies the new theme being requested and the current theme is still displayed under the Cookie header.
   
   ```http
   GET /fdf/?theme=default HTTP/1.1
   ...
   Cookie: theme=blue
   ```

4. Yes.

5. Via the Cookie in the browser's storage.

6. It is presented in the GET request header.

7. Change
   
   ```html
   <main class="container blue">
   ```
   
   to
   
   ```html
   <main class="container red">
   ```

8. Adjust the GET header to set the theme to another color.

9. `~/.mozilla/firefox/*.default/Cache`

### Part 2: Cross-site Scripting

1. Beginning with a user writing the body of their post, it is possible for them to inject html code into the page containing the post by disguising a part of their post in tags. It's similar to a SQL injection attack. Part of the signifigance of this type of attack is it is executed when someone else selects their post and the server returns the html containing their post (and the disguised html), so it can lie in wait for a while.

2. It would be quite easy for Moriarty to redirect a user who clicks on their post to an insecure webpage of their choosing where they can fall prey to any number of social engineered scams or input sensitive information.

3. They could potentially use JavaScript to activate some kind of key logger that captures the user's passwords or other sensitive information.

4. The browser can parse input for malicious code similar to screening for SQL injections.






















































