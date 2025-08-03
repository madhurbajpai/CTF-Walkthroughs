Before checking this walkthrough, try to solve the level on your own. In this level, you see the message:  
**Access disallowed. You are visiting from "" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/".**

This is a hint: the site checks the **Referer** header in your request. To bypass this, you need to set the Referer header to `http://natas5.natas.labs.overthewire.org/`.

There are two common ways to do this:

1. **Using Burp Suite:**
    - Open Burp Suite and enable intercept.
    - Refresh the page in your browser.
    - In Burp, find the intercepted request and change the Referer header to `http://natas5.natas.labs.overthewire.org/`.
    - Forward the request. You should now see the password.

2. **Using Browser Developer Tools:**
    - Open Developer Tools (usually F12 or right-click → Inspect).
    - Go to the **Network** tab and refresh the page.
    - Find the `index.php` request, right-click, and select **Copy as cURL**.
    - Paste the cURL command into a text editor, then copy it again as a single line.
    - Edit the command to add or modify the `Referer` header:
      ```
      -H "Referer: http://natas5.natas.labs.overthewire.org/"
      ```
    - Run the command in your terminal to get the password.

Once you have the flag, proceed to the next level with these credentials:

- **Username:** natas3  
- **URL:** [http://natas5.natas.labs.overthewire.org/](http://natas5.natas.labs.overthewire.org/)  
- **Password:** (The flag you just found)
