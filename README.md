<h3>Introduction</h3>
<p>The Utilities Framework is a set of Php libraries that provide functions such as error handling, logding, emailing, fetching web pages, script profiling, database abstraction, encryption, template engine and more. It requires Php 7.2 and above. The libraries are easy to use and can be used with custom applications and Php Frameworks</p>

<p>The Utilities Framework code is fully commented and compliant with the <a href='https://www.php-fig.org/psr/psr-2/'>PSR-2</a> coding guidelines.</p>

<h3>Features</h3>
<p>The Utilities Framework has the following features:</p>
<ol>
  <li>
    <h5>Database Management</h5>
    <p>It provides functions for working with Databases. It consists of a Query Builder, Database Cache Manager and Database Log Manager. It also provides a Database MetaQuery Runner and Database Transaction Manager, based on <a href='http://php.net/manual/en/book.pdo.php'>PDO</a></p>
  </li>
  <li>
    <h5>Method Validation</h5>
    <p>This allows validating method parameter values against information in the method's Doc Block comments. This feature is provided by the <a href='/articles/view/254/comment-manager'>Comment Manager</a> package.</p>
  </li>
  <li>
    <h5>Error Management</h5>
    <p>It allows application errors to be displayed using html template files. The template files can be easily customized. Default template files are provided for displaying formatted error messages for the browser and the command line</p>
  </li>
  <li>
    <h5>File and Folder Management</h5>
    <p>It provides functions for fetching url contents, checking if network connection works, searching for files with a folder and copying folder contents recursively</p>
  </li>
  <li>
    <h5>Email Handling</h5>
    <p>It provides functions for sending email in plain text format and html format with file attachments. It is based on the <a href='https://pear.php.net/package/Mail/'>Pear Mail</a> library and hence supports sending email using SMTP server, Php mail function and Sendmail library</p>
  </li>
  <li>
    <h5>Log Management</h5>
    <p>It provides functions for saving and updating log data to database. It uses the PDO library for saving data and hence allows log data to be saved to all the databases that are supported by PDO</p>
  </li>
  <li>
    <h5>Template Engine</h5>
    <p>It provides a template engine that allows separating the html layout code from the data. It also allows templates to be built recursively. This means that a template can consist of one or more templates, which can contain more templates. This allows complex website layouts to be divided in to simple layout files that are automatically combined by the template engine</p>
  </li>
  <li>
    <h5>Encryption</h5>
    <p>It provides function for encrypting and decrypting data using the new <a href='http://php.net/manual/en/book.sodium.php'>LibSodium library</a>, which is part of Php >=7.2</p>
  </li>
  <li>
    <h5>String Utilities</h5>
    <p>It provides functions for exporting data to RSS format, converting relative urls to absolute, checking if string is valid JSON, HTML or Base64 encoded and more</p>
  </li>
  <li>
    <h5>Profiler</h5>
    <p>It allows the memory usage and execution time to be measured between function calls</p>
  </li>
  <li>
    <h5>Cache Manager</h5>
    <p>It allows data to be stored in a cache. It supports memory cache and database cache</p>
  </li>
  <li>
    <h5>Authentication</h5>
    <p>It provides functions for authenticating users using http digest authentication</p>
  </li>
</ol>

<h3 class="mb-4">Installation</h3>

<ol>

<li>
<h5>Install using composer:</h5>
<p>Run the command: <b>composer require nadirlc/utilities-framework</b></p>
<p><b>OR</b></p>
</li>

<li>
<h5>Download from GitHub</h5>
<p>Run the command: <b>git clone https://github.com/nadirlc/utilities-framework.git</b></p>
</li>
</ol>

<h3>Usage</h3>
<p>All components of the Utilities Framework can be accessed using factory functions. To use a feature, we need to first create an object of the relavant component. For example: <b>UtilitiesFramework::Factory("email", $parameters);</b>. To send an email the following code can be used:</p>

<pre id="example1" class="collapse"><b>
/* The Email class requires Mail and Mail_Mime pear package */
include_once (&#x22;Mail.php&#x22;);
include_once (&#x22;Mail/mime.php&#x22;);
        
/* Change the from and to emails to your email address */
$from_email       = &#x22;nadir@dev.pakjiddat.pk&#x22;;
$to_email         = &#x22;nadir@dev.pakjiddat.pk&#x22;;
/** The parameters for the email object */
$parameters       = array(&#x22;params&#x22; =&#x3E; &#x22;&#x22;, &#x22;backend&#x22; =&#x3E; &#x22;mail&#x22;);
/* The Email class object is fetched */
$email            = UtilitiesFramework::Factory(&#x22;email&#x22;, $parameters);
/** The email is sent */
$is_sent          = $email-&#x3E;SendEmail($from_email, $to_email, &#x22;Utilitiesframework Test&#x22;,
                        &#x22;&#x3C;h3&#x3E;test html content&#x3C;/h3&#x3E;&#x22;, 
                        null,
                        array(&#x22;file-path&#x22;)
                    );
/** If the email was sent, then information message is shown */
if ($is_sent) echo &#x22;Email was successfully sent&#x22;;
else echo &#x22;Email could not be sent&#x22;;
</b></pre>


<h3>Examples</h3>
<p>The <b>/examples</b> folder contains example usage for each component</p>
