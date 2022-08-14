---
title: Node 개발 환경을 설치하기
slug: Learn/Server-side/Express_Nodejs/development_environment
tags:
  - CodingScripting
  - Express
  - Node
  - nodejs
  - npm
  - 개발 환경
  - 배움
  - 서버-사이드
  - 인트로
  - 초보자
translation_of: Learn/Server-side/Express_Nodejs/development_environment
original_slug: Learn/Server-side/Express_Nodejs/개발_환경
---
<div>{{LearnSidebar}}</div>

<div>{{PreviousMenuNext("Learn/Server-side/Express_Nodejs/Introduction", "Learn/Server-side/Express_Nodejs/Tutorial_local_library_website", "Learn/Server-side/Express_Nodejs")}}</div>

<p class="summary">이제 Express에 관한 내용을 알았으니, Windows, Linux (Ubuntu), 그리고 macOS 에서의 Node/Express 개발 환경을 설정하고 테스트하는 법을 보여드리겠습니다. 사용중인 운영 체제가 무엇이든 간에, 이 글은 당신에게 Express 앱 개발을 시작할 수 있도록 필요한 내용을 제공합니다.</p>

<table class="learn-box standard-table">
 <tbody>
  <tr>
   <th scope="row">전제 조건:</th>
   <td>터미널 혹은 명령어 창을 여는 방법. 당신의 개발 컴퓨터의 운영 체제에 소프트웨어 패키지를 설치하는 방법을 알고 있어야 합니다.</td>
  </tr>
  <tr>
   <th scope="row">목표:</th>
   <td>당신의 컴퓨터에 Express (X.XX) 을 위한 개발 환경을 설치하는 것.</td>
  </tr>
 </tbody>
</table>

<h2 id="Express_개발_환경_개요">Express 개발 환경 개요</h2>

<p>Node와 Express를 통해 웹앱 개발을 한결 수월하게 할 수 있습니다. 이 섹션에서는 어떤 도구들이 필요한지, Ubuntu, macOS, 그리고 Windows에서 어떻게 Node와 Express를 설치하는지, 마지막으로, 설치 후 어떻게 테스트해볼 수 있는지 살펴볼 것입니다.</p>

<h3 id="Express_개발_환경이란_무엇입니까">Express 개발 환경이란 무엇입니까?</h3>

<p>Express개발환경은 Nodejs의 설치, NPM 패키지 매니저, 그리고 (선택적) 로컬 컴퓨터의 <em>Express Application Generator</em>를<em> </em>포함합니다.</p>

<p><em>Node</em> and the <em>NPM</em> package manager are installed together from prepared binary packages, installers, operating system package managers or from source (as shown in the following sections). <em>Express</em> is then installed by NPM as a dependency of your individual <em>Express</em> web applications (along with other libraries like template engines, database drivers, authentication middleware, middleware to serve static files, etc.)</p>

<p><em>NPM</em> can also be used to (globally) install the <em>Express Application Generator</em>, a handy tool for creating skeleton <em>Express</em> web apps that follow the <a href="https://developer.mozilla.org/en-US/docs/Glossary/MVC">MVC pattern</a>. The application generator is optional because you don't <em>need</em> to use this tool to create apps that use Express, or construct Express apps that have the same architectural layout or dependencies. We'll be using it though, because it makes getting started a lot easier, and promotes a modular application structure.</p>

<div class="note">
<p><strong>Note:</strong> Unlike for some other web frameworks, the development environment does not include a separate development web server. In <em>Node</em>/<em>Express</em> a web application creates and runs its own web server!</p>
</div>

<p>There are other peripheral tools that are part of a typical development environment, including <a href="/en-US/docs/Learn/Common_questions/Available_text_editors">text editors</a> or IDEs for editing code, and source control management tools like <a href="https://git-scm.com/">Git</a> for safely managing different versions of your code. We are assuming that you've already got these sorts of tools installed (in particular a text editor).</p>

<h3 id="What_operating_systems_are_supported">What operating systems are supported?</h3>

<p><em>Node</em> can be run on Windows, macOS, many "flavours" of Linux, Docker, etc. (there is a full list on the nodejs <a href="https://nodejs.org/en/download/">Downloads</a> page). Almost any personal computer should have the necessary performance to run Node during development. <em>Express</em> is run in a <em>Node</em> environment, and hence can run on any platform that runs <em>Node</em>.</p>

<p>이 기사에서는 Windows, macOS, 그리고 Ubuntu Linux에서의 설치방법을 안내해드리고 있습니다.</p>

<h3 id="What_version_of_NodeExpress_should_you_use">What version of Node/Express should you use?</h3>

<p>There are many <a href="https://nodejs.org/en/blog/release/">releases of Node</a> — newer releases contain bug fixes, support for more recent versions of ECMAScript (JavaScript) standards, and improvements to the Node APIs. </p>

<p>Generally you should use the most recent <em>LTS (long-term supported)</em> release as this will be more stable than the "current" release while still having relatively recent features (and is still being actively maintained). You should use the <em>Current</em> release if you need a feature that is not present in the LTS version.</p>

<p>For <em>Express</em> you should always use the latest version.</p>

<h3 id="What_about_databases_and_other_dependencies">What about databases and other dependencies?</h3>

<p>Other dependencies, such as database drivers, template engines, authentication engines, etc. are part of the application, and are imported into the application environment using the NPM package manager.  We'll discuss them in later app-specific articles.</p>

<h2 id="Node_설치하기">Node 설치하기</h2>

<p><em>Express</em> 를 사용하기 위해서 우선 운영체제에 <em>Nodejs</em>와 <a href="https://docs.npmjs.com/">Node Package Manager (NPM)</a>를 설치해야 합니다. The following sections explain the easiest way to install the Long Term Supported (LTS) version of Nodejs on Ubuntu Linux 16.04, macOS, and Windows 10.</p>

<div class="note">
<p><strong>Tip:</strong> The sections below show the easiest way to install <em>Node</em> and <em>NPM</em> on our target OS platforms. If you're using another OS or just want to see some of the other approaches for the current platforms then see <a href="https://nodejs.org/en/download/package-manager/">Installing Node.js via package manager</a> (nodejs.org).</p>
</div>

<h3 id="Windows_and_macOS">Windows and macOS</h3>

<p><em>Node</em>와 <em>NPM</em>을 설치하는 것은 간단합니다:</p>

<ol>
 <li>Installer를 다운받읍시다:
  <ol>
   <li><a href="https://nodejs.org/en/">https://nodejs.org/en/</a></li>
   <li>"안정적이고 신뢰도가 높은" LTS버튼을 클릭해 다운로드를 시작합니다. .</li>
  </ol>
 </li>
 <li>다운로드된 파일을 더블클릭해 Node를 설치합니다.</li>
</ol>

<p>The easiest way to install the most recent LTS version of Node 10.x is to use the <a href="https://nodejs.org/en/download/package-manager/#debian-and-ubuntu-based-linux-distributions">package manager</a> to get it from the Ubuntu <em>binary distributions</em> repository. This can be done very simply by running the following two commands on your terminal:</p>

<pre class="brush: bash notranslate">curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
</pre>

<div class="warning">
<p><strong>Warning:</strong> Don't install directly from the normal Ubuntu repositories because they contain very old versions of node.</p>
</div>

<ol>
</ol>

<h3 id="Nodejs와_NPM_테스팅">Nodejs와 NPM 테스팅</h3>

<p>The easiest way to test that node is installed is to run the "version" command in your terminal/command prompt and check that a version string is returned:</p>

<pre class="brush: bash notranslate">&gt;node -v
v10.15.1</pre>

<p>The <em>Nodejs</em> package manager <em>NPM</em> should also have been installed, and can be tested in the same way:</p>

<pre class="brush: bash notranslate">&gt;npm -v
6.4.1</pre>

<p>As a slightly more exciting test let's create a very basic "pure node" server that simply prints out "Hello World" in the browser when you visit the correct URL in your browser:</p>

<ol>
 <li>Copy the following text into a file named <strong>hellonode.js</strong>. This uses pure <em>Node</em> features (nothing from Express) and some ES6 syntax:

  <pre class="brush: js notranslate">//Load HTTP module
const http = require("http");
const hostname = '127.0.0.1';
const port = 3000;

//Create HTTP server and listen on port 3000 for requests
const server = http.createServer((req, res) =&gt; {

  //Set the response HTTP header with HTTP status and Content type
  res.statusCode = 200;
  res.setHeader('Content-Type', 'text/plain');
  res.end('Hello World\n');
});

//listen for request on port 3000, and as a callback function have the port listened on logged
server.listen(port, hostname, () =&gt; {
  console.log(`Server running at http://${hostname}:${port}/`);
});
</pre>

  <p>The code imports the "http" module and uses it to create a server (<code>createServer()</code>) that listens for HTTP requests on port 3000. The script then prints a message to the console about what browser URL you can use to test the server. The <code>createServer()</code> function takes as an argument a callback function that will be invoked when an HTTP request is received — this simply returns a response with an HTTP status code of 200 ("OK") and the plain text "Hello World".</p>

  <div class="note">
  <p><strong>Note:</strong>  Don't worry if you don't understand exactly what this code is doing yet! We'll explain our code in greater detail once we start using Express!</p>
  </div>
 </li>
 <li>Start the server by navigating into the same directory as your <code>hellonode.js</code> file in your command prompt, and calling <code>node</code> along with the script name, like so:
  <pre class="brush: bash notranslate">&gt;node hellonode.js
Server running at http://127.0.0.1:3000/
</pre>
 </li>
 <li>Navigate to the URL <a href="http://127.0.0.1:3000">http://127.0.0.1:3000 </a>. If everything is working, the browser should simply display the string "Hello World".</li>
</ol>

<h2 id="Using_NPM">Using NPM</h2>

<p>Next to <em>Node</em> itself, <a href="https://docs.npmjs.com/">NPM</a> is the most important tool for working with<em> Node </em>applications. NPM is used to fetch any packages (JavaScript libraries) that an application needs for development, testing, and/or production, and may also be used to run tests and tools used in the development process. </p>

<div class="note">
<p><strong>Note:</strong> From Node's perspective, <em>Express</em> is just another package that you need to install using NPM and then require in your own code.</p>
</div>

<p>You can manually use NPM to separately fetch each needed package. Typically we instead manage dependencies using a plain-text definition file named <a href="https://docs.npmjs.com/files/package.json">package.json</a>. This file lists all the dependencies for a specific JavaScript "package", including the package's name, version, description, initial file to execute, production dependencies, development dependencies, versions of <em>Node</em> it can work with, etc. The <strong>package.json</strong> file should contain everything NPM needs to fetch and run your application (if you were writing a reusable library you could use this definition to upload your package to the npm respository and make it available for other users).</p>

<h3 id="dependencies_추가">dependencies 추가</h3>

<p>The following steps show how you can use NPM to download a package, save it into the project dependencies, and then require it in a Node application.</p>

<div class="note">
<p><strong>Note:</strong> Here we show the instructions to fetch and install the <em>Express</em> package. Later on we'll show how this package, and others, are already specified for us using the <em>Express Application Generator</em>. This section is provided because it is useful to understand how NPM works and what is being created by the application generator.</p>
</div>

<ol>
 <li>First create a directory for your new application and navigate into it:
  <pre class="brush: bash notranslate">mkdir myapp
cd myapp</pre>
 </li>
 <li>Use the npm <code>init</code> command to create a <strong>package.json</strong> file for your application. This command prompts you for a number of things, including the name and version of your application and the name of the initial entry point file (by default this is <strong>index.js</strong>). For now, just accept the defaults:
  <pre class="brush: bash notranslate">npm init</pre>

  <p>If you display the <strong>package.json</strong> file (<code>cat package.json</code>), you will see the defaults that you accepted, ending with the license.</p>

  <pre class="brush: json notranslate">{
  "name": "myapp",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" &amp;&amp; exit 1"
  },
  "author": "",
  "license": "ISC"
}
</pre>
 </li>
 <li>Now install Express in the <code>myapp</code> directory and save it in the dependencies list of your <strong>package.json</strong> file</li>
 <li>
  <pre class="brush: bash notranslate">npm install express</pre>

  <p>The dependencies section of your <strong>package.json</strong> will now appear at the end of the <strong>package.json</strong> file and will include <em>Express</em>.</p>

  <pre class="brush: json notranslate">{
  "name": "myapp",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" &amp;&amp; exit 1"
  },
  "author": "",
  "license": "ISC",
<strong>  "dependencies": {
    "express": "^4.16.4"
  }</strong>
}
</pre>
 </li>
 <li>To use the Express library you call the <code>require()</code> function in your index.js file to include it in your application. Create this file now, in the root of the "myapp" application directory, and give it the following contents:
  <pre class="brush: js notranslate">const express = require('express')
const app = express();

app.get('/', (req, res) =&gt; {
  res.send('Hello World!')
});

app.listen(8000, () =&gt; {
  console.log('Example app listening on port 8000!')
});
</pre>

  <p>This code shows a minimal "HelloWorld" Express web application. This imports the "express" module using <code>require()</code> and uses it to create a server (<code>app</code>) that listens for HTTP requests on port 8000 and prints a message to the console explaining what browser URL you can use to test the server. The <code>app.get()</code> function only responds to HTTP <code>GET</code> requests with the specified URL path ('/'), in this case by calling a function to send our <em>Hello World!</em> message.</p>
 </li>
 <li>You can start the server by calling node with the script in your command prompt:
  <pre class="brush: bash notranslate">&gt;node index.js
Example app listening on port 8000
</pre>
 </li>
 <li>Navigate to the URL (<a href="http://127.0.0.1:8000/">http://127.0.0.1:8000/</a>). If everything is working, the browser should simply display the string "Hello World!".</li>
</ol>

<h3 id="Development_dependencies">Development dependencies</h3>

<p>If a dependency is only used during development, you should instead save it as a "development dependency" (so that your package users don't have to install it in production). For example, to use the popular JavaScript Linting tool <a href="http://eslint.org/">eslint</a> you would call NPM as shown:</p>

<pre class="brush: bash notranslate"><code>npm install eslint --save-dev</code></pre>

<p>The following entry would then be added to your application's <strong>package.json</strong>:</p>

<pre class="brush: js notranslate">  "devDependencies": {
    "eslint": "^4.12.1"
  }
</pre>

<div class="note">
<p><strong>Note:</strong> "<a href="https://en.wikipedia.org/wiki/Lint_(software)">Linters</a>" are tools that perform static analysis on software in order to recognise and report adherence/non-adherance to some set of coding best practice.</p>
</div>

<h3 id="Running_tasks">Running tasks</h3>

<p>In addition to defining and fetching dependencies you can also define <em>named</em> scripts in your <strong>package.json</strong> files and call NPM to execute them with the <a href="https://docs.npmjs.com/cli/run-script">run-script</a> command. This approach is commonly used to automate running tests and parts of the development or build toolchain (e.g., running tools to minify JavaScript, shrink images, LINT/analyse your code, etc).</p>

<div class="note">
<p><strong>Note:</strong> Task runners like <a href="http://gulpjs.com/">Gulp</a> and <a href="http://gruntjs.com/">Grunt</a> can also be used to run tests and other external tools.</p>
</div>

<p>For example, to define a script to run the <em>eslint</em> development dependency that we specified in the previous section we might add the following script block to our <strong>package.json</strong> file (assuming that our application source is in a folder /src/js):</p>

<pre class="brush: js notranslate">"scripts": {
  ...
  "lint": "eslint src/js"
  ...
}
</pre>

<p>To explain a little further, <code>eslint src/js</code> is a command that we could enter in our terminal/command line to run <code>eslint</code> on JavaScript files contained in the <code>src/js</code> directory inside our app directory. Including the above inside our app's package.json file provides a shortcut for this command — <code>lint</code>.</p>

<p>We would then be able to run <em>eslint</em> using NPM by calling:</p>

<pre class="brush: bash notranslate"><code>npm run-script lint
# OR (using the alias)
npm run lint</code>
</pre>

<p>This example may not look any shorter than the original command, but you can include much bigger commands inside your npm scripts, including chains of multiple commands. You could identify a single npm script that runs all your tests at once.</p>

<h2 id="Installing_the_Express_Application_Generator">Installing the Express Application Generator</h2>

<p>The <a href="https://expressjs.com/en/starter/generator.html">Express Application Generator</a> tool generates an Express application "skeleton". Install the generator using NPM as shown (the <code>-g</code> flag installs the tool globally so that you can call it from anywhere):</p>

<pre class="notranslate"><code>npm install express-generator -g</code></pre>

<p>To create an <em>Express</em> app named "helloworld" with the default settings, navigate to where you want to create it and run the app as shown:</p>

<pre class="brush: bash notranslate">express helloworld</pre>

<div class="note">
<p><strong>Note: </strong>You can also specify the template library to use and a number of other settings. Use the <code>help</code> command to see all the options:</p>

<pre class="brush: bash notranslate">express --help
</pre>
</div>

<p>NPM will create the new Express app in a sub folder of your current location, displaying build progress on the console. On completion, the tool will display the commands you need to enter to install the Node dependencies and start the app.</p>

<div class="note">
<p>The new app will have a <strong>package.json</strong> file in its root directory. You can open this to see what dependencies are installed, including Express and the template library Jade:</p>

<pre class="brush: js notranslate">{
  "name": "helloworld",
  "version": "0.0.0",
  "private": true,
  "scripts": {
    "start": "node ./bin/www"
  },
  "dependencies": {
    "cookie-parser": "~1.4.3",
    "debug": "~2.6.9",
    "express": "~4.16.0",
    "http-errors": "~1.6.2",
    "jade": "~1.11.0",
    "morgan": "~1.9.0"
  }
}
</pre>


</div>

<p>Install all the dependencies for the helloworld app using NPM as shown:</p>

<pre class="brush: bash notranslate">cd helloworld
npm install
</pre>

<p>Then run the app (the commands are slightly different for Windows and Linux/macOS), as shown below:</p>

<pre class="brush: bash notranslate"># Run the helloworld on Windows with Command Prompt
SET DEBUG=helloworld:* &amp; npm start

# Run the helloworld on Windows with PowerShell
SET DEBUG=helloworld:* | npm start

# Run helloworld on Linux/macOS
DEBUG=helloworld:* npm start
</pre>

<p>The DEBUG command creates useful logging, resulting in an output like that shown below.</p>

<pre class="brush: bash notranslate">&gt;SET DEBUG=helloworld:* &amp; npm start

&gt; helloworld@0.0.0 start D:\Github\expresstests\helloworld
&gt; node ./bin/www

  helloworld:server Listening on port 3000 +0ms</pre>

<p>Open a browser and navigate to <a href="http://127.0.0.1:3000/">http://127.0.0.1:3000/</a> to see the default Express welcome page.</p>

<p><img alt="Express - Generated App Default Screen" src="https://mdn.mozillademos.org/files/14331/express_default_screen.png" style="border-style: solid; border-width: 1px; display: block; height: 301px; margin: 0px auto; width: 675px;"></p>

<p>We'll talk more about the generated app when we get to the article on generating a skeleton application.</p>

<ul>
</ul>

<h2 id="Summary">Summary</h2>

<p>You now have a Node development environment up and running on your computer that can be used for creating Express web applications. You've also seen how NPM can be used to import Express into an application, and also how you can create applications using the Express Application Generator tool and then run them.</p>

<p>In the next article we start working through a tutorial to build a complete web application using this environment and associated tools.</p>

<h2 id="See_also">See also</h2>

<ul>
 <li><a href="https://nodejs.org/en/download/">Downloads</a> page (nodejs.org)</li>
 <li><a href="https://nodejs.org/en/download/package-manager/">Installing Node.js via package manager</a> (nodejs.org)</li>
 <li><a href="http://expressjs.com/en/starter/installing.html">Installing Express</a> (expressjs.com)</li>
 <li><a href="https://expressjs.com/en/starter/generator.html">Express Application Generator</a> (expressjs.com)</li>
</ul>

<p>{{PreviousMenuNext("Learn/Server-side/Express_Nodejs/Introduction", "Learn/Server-side/Express_Nodejs/Tutorial_local_library_website", "Learn/Server-side/Express_Nodejs")}}</p>



<h2 id="In_this_module">In this module</h2>

<ul>
 <li><a href="/en-US/docs/Learn/Server-side/Express_Nodejs/Introduction">Express/Node introduction</a></li>
 <li><a href="/en-US/docs/Learn/Server-side/Express_Nodejs/development_environment">Setting up a Node (Express) development environment</a></li>
 <li><a href="/en-US/docs/Learn/Server-side/Express_Nodejs/Tutorial_local_library_website">Express Tutorial: The Local Library website</a></li>
 <li><a href="/en-US/docs/Learn/Server-side/Express_Nodejs/skeleton_website">Express Tutorial Part 2: Creating a skeleton website</a></li>
 <li><a href="/en-US/docs/Learn/Server-side/Express_Nodejs/mongoose">Express Tutorial Part 3: Using a Database (with Mongoose)</a></li>
 <li><a href="/en-US/docs/Learn/Server-side/Express_Nodejs/routes">Express Tutorial Part 4: Routes and controllers</a></li>
 <li><a href="/en-US/docs/Learn/Server-side/Express_Nodejs/Displaying_data">Express Tutorial Part 5: Displaying library data</a></li>
 <li><a href="/en-US/docs/Learn/Server-side/Express_Nodejs/forms">Express Tutorial Part 6: Working with forms</a></li>
 <li><a href="/en-US/docs/Learn/Server-side/Express_Nodejs/deployment">Express Tutorial Part 7: Deploying to production</a></li>
</ul>