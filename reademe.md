## Deploy Lambda to AWS via AWS CLI

#### NOTE : Follow these steps to zip your lambda and upload to AWS

1. Put your Lambda function file(s) in a separate directory. This is because you install npm packages locally for Lambda and you want to be able to isolate and test what you will upload to Lambda.

2. Install your NPM packages locally with npm install packageName while you're in your separate Lambda directory you created in step #1.

3. Make sure your function works when running locally: node lambdaFunc.js (you can simply comment out the two export.handler lines in your code to adapt your code to run with Node locally).

4. Go to the Lambda's directory and compress the contents by running : zip -r lambdaFunc.zip .

- make sure not to include the directory itself -- run :

5. If you have the aws-cli installed, which I suggest having if you want to make your life easier, you can now enter this command:
   **aws lambda update-function-code --function-name lambdaFunc \
   --zip-file fileb:///User/to/your/lambdaFunc.zip**

6. Now you can click test in the Lambda console.

7. Your Lambda should be deployed
