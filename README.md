# ece568-lab-2-openssl-programming-solved
**TO GET THIS SOLUTION VISIT:** [ECE568 Lab 2-OpenSSL Programming Solved](https://www.ankitcodinghub.com/product/ece568-lab-2-openssl-programming-solved/)


---

📩 **If you need this solution or have special requests:** **Email:** ankitcoding@gmail.com  
📱 **WhatsApp:** +1 419 877 7882  
📄 **Get a quote instantly using this form:** [Ask Homework Questions](https://www.ankitcodinghub.com/services/ask-homework-questions/)

*We deliver fast, professional, and affordable academic help.*

---

<h2>Description</h2>



<div class="kk-star-ratings kksr-auto kksr-align-center kksr-valign-top" data-payload="{&quot;align&quot;:&quot;center&quot;,&quot;id&quot;:&quot;119950&quot;,&quot;slug&quot;:&quot;default&quot;,&quot;valign&quot;:&quot;top&quot;,&quot;ignore&quot;:&quot;&quot;,&quot;reference&quot;:&quot;auto&quot;,&quot;class&quot;:&quot;&quot;,&quot;count&quot;:&quot;1&quot;,&quot;legendonly&quot;:&quot;&quot;,&quot;readonly&quot;:&quot;&quot;,&quot;score&quot;:&quot;5&quot;,&quot;starsonly&quot;:&quot;&quot;,&quot;best&quot;:&quot;5&quot;,&quot;gap&quot;:&quot;4&quot;,&quot;greet&quot;:&quot;Rate this product&quot;,&quot;legend&quot;:&quot;5\/5 - (1 vote)&quot;,&quot;size&quot;:&quot;24&quot;,&quot;title&quot;:&quot;ECE568  Lab 2-OpenSSL Programming Solved&quot;,&quot;width&quot;:&quot;138&quot;,&quot;_legend&quot;:&quot;{score}\/{best} - ({count} {votes})&quot;,&quot;font_factor&quot;:&quot;1.25&quot;}">

<div class="kksr-stars">

<div class="kksr-stars-inactive">
            <div class="kksr-star" data-star="1" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="2" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="3" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="4" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" data-star="5" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>

<div class="kksr-stars-active" style="width: 138px;">
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
            <div class="kksr-star" style="padding-right: 4px">


<div class="kksr-icon" style="width: 24px; height: 24px;"></div>
        </div>
    </div>
</div>


<div class="kksr-legend" style="font-size: 19.2px;">
            5/5 - (1 vote)    </div>
    </div>
Introduction

To complete this lab, you will have to learn how to use the OpenSSL library, which is installed on ECF. You are provided with code for a simple client and a simple server application, with an accompanying Makefile. You are also provided with a set of key files that will be used for authentication purposes.

Overview of files provided server.c

The server takes as input a port (defaults to 8765). It then binds to this port and waits for connections. Upon connection of a client, a child is forked to handle the session. The server receives a message, whose length is at most 255 characters, prints this message to stdout, and then sends an answer to the client.

client.c

The client takes as input a host and a port (defaults to localhost and 8765). It connects to that host, sends a message, then reads from the socket. Upon receipt of a message from the server, of length at most 255 characters, it displays the message on stdout and exits.

Key files

Three key files are provided: 568ca.pem, alice.pem and bob.pem (x509 certificates). 568ca.pem contains the public key of the certificate authority (CA) ece568, which can be used to verify the authenticity of both the client and the server’s public keys. The password (key phrase) for the certificates (both Alice’s and Bob’s) is “password”. Bob is running the server, and Alice is running the client.

You will need to generate additional key pairs and certificates for testing. This can be done by using the openssl command line tool. The example below will give you an idea of how to use the command line tool. For more help, please refer to the resources section.

Creating a root certificate

openssl req -new -x509 -extensions v3_ca -keyout &lt;ca_private_key.pem&gt; -out &lt;certificate.pem&gt; -days 365 -config &lt;openssl_config_file&gt; where:

ca_private_key.pem: Certificate Authority’s private key. certificate.pem: Certificate Authority’s certificate. openssl_config_file: See resources for a configuration file example.

Creating a signing request and public/private key pair

where:

name-req.pem: signing request name-private.pem: private key

Signing a public key

Viewing a certificate

Your Task

Client Specification

1. Only communicate with servers using SSLv3 or TLSv1. If the server does not support one of those protocols, then print:

2. Only communicate with a protocol that uses the SHA1 hash function. If server does not use SHA1, then print:

3. Only communicate with Bob’s Server by checking that the Common Name (CN) of the server matches “Bob’s Server”, and that the e-mail address of the server certificate subject matches “ece568bob@ecf.utoronto.ca

(mailto:ece568bob@ecf.utoronto.ca) ”. The client must verify that the server’s certificate has a valid signature from the CA.

If both CN and Email are correct, then print the server information, request sent, and response returned by the server:

4. The client should shutdown the SSL connection correctly.

5. The client should report if the server does not shutdown correctly. If this happens, it should print:

Server Specification

Every message the server prints should be preceded with the string ECE568-SERVER. Your server must do the following:

1. The server must support SSLv2, SSLv3 and TLSv1.

2. The server must support all cipher suites available for SSLv2, SSLv3 and TLSv1.

3. The server should only communicate with clients with a valid certificate signed by the CA:

If the client certificate is not signed by the proper CA the server should print:

4. If the client has a valid certificate, the server should print the CN and Email of the client, as well as the client request and server response:

5. The server should shutdown the connection properly.

6. The server should report of the client does not shutdown correctly. If this happens, it should print:

In addition, please explain what you did, in at most 300 words. These explanations must be in the file explanations_lab2.txt along with the identities of your group members just as in previous labs.

Resources

The following resources will be very useful. Please take the time to read them.

ssl

x509 ciphers

BIO_new_socket

SSL_connect

SSL_read

SSL_write

SSL_shutdown

SSL_CTX_set_verify

SSL_get_verify_result SSL_CTX_set_cipher_list openssl/objects.h

SSL_CTX_new

SSL_CTX_set_options

2. The openssl utility on ECF can be used to verify certificates, as well as generate your public/private key pairs and certificates for testing.

3. Certificate generation and signing tutorial https://www.digitalocean.com/community/tutorials/openssl-essentials-working-with-ssl-certificates-private-keys-and-csrs (https://www.digitalocean.com/community/tutorials/openssl-essentials-working-with-ssl-certificates-private-keys-and-csrs) https://www.keycdn.com/blog/openssl-tutorial (https://www.keycdn.com/blog/openssl-tutorial)

http://www.flatmtn.com/article/setting-openssl-create-certificates.html (http://www.flatmtn.com/article/setting-openssl-createcertificates.html) http://www.flatmtn.com/article/creating-pkcs12-certificates.html (http://www.flatmtn.com/article/creating-pkcs12certificates.html)

4. Read an introduction to OpenSSL programming:

http://www.linuxjournal.com/article/4822 (http://www.linuxjournal.com/article/4822) http://www.linuxjournal.com/article/5487 (http://www.linuxjournal.com/article/5487)

Submission and Marking

Please explain in at most 300 words, what you did to get the lab working. These explanations must be in the file explanations_lab2.txt, which must also contain the names and student numbers of your group members prefixed by # and separated by commas. Do not prefix other lines by # as this would confuse the automated marking scripts.

Before submitting, you should test that your submission is formatted properly with the commands

Go to the lab directory and type this command. Do not submit until the script indicates that the submission appears to be properly formatted. In addition, check that the script correctly identifies your group members.

To submit your work, run the command
