# pythonAPI
Accessing API on localhost
Downloading and using Ngrok(free command line tool that allows you to expose a service running on your local machine to the internet)
HTTP Echo Server
After installing ngrok run the following command 
ngrok http <port number>
Testing the API
We will use apibot to test some of the end points of the api. For this purpose we will create a simple graph which sends an HTTP request to authenticate with the API
 Start APibot and click 'create new graph' button. This will create an empty graph. Graph in apibot are analogous to "tests" or "workflows"
We now need to create a config node. The config node makes it possible to define variables which can later be accessed from other nodes.
Add a config node to the graph and enter the following property:
key: root, value: https://<subdomain>.ngrok.io
Image for post
configuration node
Make sure you replace <subdomain> with your ngrok subdomain.
Step #3: The HTTP request
Add an HTTP request and fill in the required arguments. This will of course depend on the API you are communicating with.
Image for post
The most important thing to notice here is that in the url field I entered ${root}/login. When a graph is executed, ${root} will be replaced with whatever you defined the root variable to be, which in our case is the ngrok URL.
Step #4: Running the graph
Click the run button. This will send the HTTP request to the ngrok URL. If you open the ngrok UI (normally running on http://127.0.0.1:4040) you will see your request.



