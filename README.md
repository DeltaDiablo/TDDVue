# TDDVuCreating a vue Project
1. install vue CLI
npm install -g @vue/cli

2. create vue project named "Client"
vue create client

3. Choose vue 3 instance for project
 vue3

4. run server for first time

npm run serve

~~you should see a result like this

~~~App running at:
~~~ - http://localhost:8080
~~~ - http://10.182.180.26:8080
~~~   Note that the development build is not optimized.
~~~   To create a production build, run npm run build.

~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

5o1. Setting your port to work on
	1. open the vue.config.js file
	2. under module.exports = defineconfig({ 
		transpileDependencies: true,
	3. type "devServer:{port:9876}"
	~~this will set the dev server to work on port 9876---pick a port that is open for use and assign it to dev server
	4. go back into client folder from terminal and run the following npm command
		npm run serve
~~~you should see a result like this
~~~App running at:
~~~  - Local:   http://localhost:9876/ 
~~~  - Network: http://10.182.180.26:9876/

~~~  Note that the development build is not optimized.
~~~  To create a production build, run npm run build.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Setting up jest and testing Library
******ADD ONLY TO DEVELOPEMNT DEPENDENCY*******
******at this time jest 26.6.3 is the only working version i have found
1. run this command
	npm install --save-dev jest@26.6.3 @testing-library/vue@next
~~~~~options short command~~~~~
	npm i -D jest@26.6.3 @testing-library/vue@next

2. run this command to install vue-jest
	npm install --save-dev vue-jest@next

3. run this command to install babel-jest version 26.6.3
	npm install --save-dev babel-jest@26.6.3

installing Axios into the client
1. run this command
	npm install axios