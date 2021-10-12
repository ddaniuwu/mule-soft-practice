# MULE SOFT PRACTICE

This practice shows some points about MuleSoft! 💻

 - Anypoint Studio 4 Linux
 - We have to extract the files from the downloaded site
 - If we use Ubuntu 20.14 just double tap in the Anypoint Studio 
 - Once made this , we just have to wait and Anypoint will init.
 - Select the defaulkt workspace / press Launch

## Link for Linux Instalation
`https://docs.mulesoft.com/studio/7.6/to-download-and-install-studio-lx`
    

## Using ANypointStudio to build an API / Testing it with Postman
  - As first step we have to create a new project 
  - After this , we give a name to our project and we can see our workspace 
  - Using an HTTP procotol we select the option in the right section and take a listener to our main section.
  - Then we select a payload to set it in the project and get a new Endpoind & asign it to our flow.
  - To run the project we just have to right click in the API building and tap run project / stop project
![](https://github.com/ddaniuwu/mule-soft-practice/blob/main/Captura%20de%20pantalla%20de%202021-10-12%2001-24-21.png)
## Testing with POSTMAN 
  - To test it we just have to go POSTMAN and page the default URL in our request input.
  - http://0.0.0.0:8081/hellomule
- ![MulesoftTest](https://github.com/ddaniuwu/mule-soft-practice/blob/main/Captura%20de%20pantalla%20de%202021-10-12%2001-32-40.png)

## Setting a secure properties step
- Once we made the process with de global elements configuration 
- We go to the scene and we drag an HTTP LIstener
![](https://github.com/ddaniuwu/mule-soft-practice/blob/main/Captura%20de%20pantalla%20de%202021-10-12%2008-43-33.png)

```
%dw 2.0
output application/json
---
[{
	FirstName: "Max",
	LastName: "Mule",
	Email: "maxthemule@mulesoft.com",
	Company: "MuleSoft"
}]

```
