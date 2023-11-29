# Deploy Serverless Flask App to Vercel for Free

> The original tutorial can be found [here](https://wisecode.blog/deploy-flask-vercel).

This repo demonstrates an example on how to deploy a Flask app to Vercel and serve it as a serverless function.

## Project Structure

```bash
flask-vercel
├── vercel.json
├── requirements.txt
└── api
    └── index.py
```

## Steps to Deploy Your Own

1. Create `vercel.json` file.

   ```json
   {
     "rewrites": [{ "source": "/(.*)", "destination": "/api/index" }]
   }
   ```

2. Create `requirements.txt` file. Can use `pip freeze > requirements.txt` to generate.

3. Create `api` folder and a simple endpoint in `index.py`.

   ```python
   from flask import Flask

   app = Flask(__name__)


   @app.route("/")
   def hello():
       return "Hello from Minh Vu!"

   ```

4. Use Vercel CLI to deploy.

   ```bash
   npm i -g vercel # Install Vercel CLI
   vercel --prod # Deploy to production, login may be required
   ```
