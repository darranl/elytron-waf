# Elytron Web Authentication Framework

This project is primariy a research project to start exploring options to improve the world of web application authentication.

At the moment in my opinion there is an over reliance on SSL/TLS to protect authentication exchanges and as a result clear text authentication mechanisms are commonly used, I see a few possible issues with this.

1. Any compromise to the keys can be used to recover passwords, this could even be from historicaly intercepted exchanges.
2. If the servers memory is compromised somehow clear text passwords may be obtainable.
3. If the server is not trustworthy or completely trusted it now has the clear text password it could use itself.

At the same time there are various RFCs proposed for stronger authentication mechanisms to be supported over HTTP, but even this has it's own problems: -

1. Virtually no implementations of proposed implementations, who implements first? Client or server? And if the other side is not implemented by should this side implement it?
2. A very strong desire for authentication to be integrated with and themed with the web application.

Even though allowing the browser to handle authentication may be stronger in that no clear text password is exchanged users will complain it does not look nice.

Another issue with browser based authentication is that it is very hard to control the lifetime of a perceived authenticated session.

# Scope

Under this project I intend to explore the following areas.

1. Stronger authentication mechanisms being made available directly to web applications (Using JavaScript or other technologies.).
 - Possible support for SASL mechanisms.
 - Implementation of proposed RFCs.
2. Integration into existing web applications, e.g. could we filter an existing login form and automatically insert support for the stronger authentication mechanisms without needing changes?
 
Various SSO technologies also have potential to assist in this area, many SSO tokens would still be vulnerable to being used in a replay attack but their lifespan is limited, comprimise the private keys used by the server or obtain access to the servers memory and there is only a limited about of information that could be used.  Secondly all the tokens can be invalidated without needing a user to change their password.  Of course there is still the original application that the user does sign into with their username and password that could benefit from the stronger authentication mechanism.

