🎯 Day 25 Task

✅ THM Room


https://tryhackme.com/room/principlesofsecurity


✅ 4.2.4 Review Old Backup and Unreferenced Files for Sensitive Information


Test Objectives
Find and analyse unreferenced files that might contain sensitive information.


How to Test

Black-Box Testing


Inference from the Naming Scheme Used for Published Content

Enumerate all of the application’s pages and functionality. This can be done manually using a browser, or using an application spidering tool. Most applications use a recognizable naming scheme, and organize resources into pages and directories using words that describe their function. From the naming scheme used for published content, it is often possible to infer the name and location of unreferenced pages. For example, if a page viewuser.asp is found, then look also for edituser.asp, adduser.asp and deleteuser.asp. If a directory /app/user is found, then look also for /app/admin and /app/manager


Other Clues in Published Content

Many web applications leave clues in published content that can lead to the discovery of hidden pages and functionality. These clues often appear in the source code of HTML and JavaScript files. The source code for all published content should be manually reviewed to identify clues about other pages and functionality. For example:


Programmers’ comments and commented-out sections of source code may refer to hidden content:

```
<!-- <A HREF="uploadfile.jsp">Upload a document to the server</A> -->
<!-- Link removed while bugs in uploadfile.jsp are fixed          -->
```
JavaScript may contain page links that are only rendered within the user’s GUI under certain circumstances:

```
var adminUser=false;
if (adminUser) menu.add (new menuItem ("Maintain users", "/admin/useradmin.jsp"));
```


HTML pages may contain FORMs that have been hidden by disabling the SUBMIT element:

```
<form action="forgotPassword.jsp" method="post">
    <input type="hidden" name="userID" value="123">
    <!-- <input type="submit" value="Forgot Password"> -->
</form>
```


Another source of clues about unreferenced directories is the /robots.txt file used to provide instructions to web robots:
```
User-agent: *
Disallow: /Admin
Disallow: /uploads
Disallow: /backup
Disallow: /~jbloggs
Disallow: /include
```

Blind Guessing

1. Identify the file extensions in use within known areas of the application (e.g. jsp, aspx, html), and use a basic wordlist appended with each of these extensions (or use a longer list of common extensions if resources permit).


2. For each file identified through other enumeration techniques, create a custom wordlist derived from that filename. Get a list of common file extensions (including ~, bak, txt, src, dev, old, inc, orig, copy, tmp, swp, etc.) and use each extension before, after, and instead of, the extension of the actual filename


Information Obtained Through Server Vulnerabilities and Misconfiguration

The most obvious way in which a misconfigured server may disclose unreferenced pages is through directory listing. Request all enumerated directories to identify any which provide a directory listing.


1. Apache ?M=D directory listing vulnerability.


3. Various IIS script source disclosure vulnerabilities.


4. IIS WebDAV directory listing vulnerabilities.


Use of Publicly Available Information

Pages that used to be referenced may still appear in the archives of Internet search engines. For example, 1998results.asp may no longer be linked from a company’s website, but may remain on the server and in search engine databases. This old script may contain vulnerabilities that could be used to compromise the entire site. The site: Google search operator may be used to run a query only against the domain of choice, such as in: site:www.example.com. Using search engines in this way has lead to a broad array of techniques which you may find useful and that are described in the Google Hacking section of this Guide. Check it to hone your testing skills via Google. Backup files are not likely to be referenced by any other files and therefore may have not been indexed by Google, but if they lie in browsable directories the search engine might know about them.


Filename Filter Bypass

Because deny list filters are based on regular expressions, one can sometimes take advantage of obscure OS filename expansion features in which work in ways the developer didn’t expect. The tester can sometimes exploit differences in ways that filenames are parsed by the application, web server, and underlying OS and it’s filename conventions.

1. Remove incompatible characters


2. Convert spaces to underscores


3. Take the first six characters of the basename


4. Add ~<digit> which is used to distinguish files with names using the same six initial characters

  
5. This convention changes after the first 3 cname ollisions

  
6. Truncate file extension to three characters

  
7. Make all the characters uppercase

  
Tools

  wget 

  nessus

  curl


Note - I am making notes from Official OWASP Website you can check it from here
https://owasp.org/www-project-web-security-testing-guide/latest/4-Web_Application_Security_Testing/ 


  I am just Sharing what I learn for help Other's !!!

#infosec #learn365 #owasp 





