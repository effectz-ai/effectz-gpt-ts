## Welcome to EffectzGPT TypeScript implementation
### EffectzGPT => Easy Workflow Automations with LLMs.
EffectzGPT helps you quickly develop **Enterprise Workflow Automation Applications** powered by **Large Language Models (LLMs)**. It is specially designed for building scalable apps that require advanced reasoning over data. It has been used in both real-world business applications and cutting-edge research. EffectzGPT makes developing powerful AI-driven workflow automation applications simple, even if you're not an AI expert. EffectzGPT has been developed using [LlamaIndex](https://github.com/run-llama/llama_index).

[This](https://github.com/effectz-ai/effectz-gpt) is the more advanced python version. The current TypeScript version doesn’t include all the advanced features available in the Python version.

This is a [LlamaIndex](https://www.llamaindex.ai/) project using [Next.js](https://nextjs.org/) 

## Getting Started

First, install the dependencies:

```
npm install
```

Second, generate the embeddings of the documents in the `./data` directory:

```
npm run generate
```

Third, run the development server:

```
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) with your browser to see the result.

You can start editing the page by modifying `app/page.tsx`. The page auto-updates as you edit the file.

This project uses [`next/font`](https://nextjs.org/docs/basic-features/font-optimization) to automatically optimize and load Inter, a custom Google Font.

## Using Docker

1. Build an image for the Next.js app:

```
docker build -t <your_app_image_name> .
```

2. Generate embeddings:

Parse the data and generate the vector embeddings if the `./data` folder exists - otherwise, skip this step:

```
docker run \
  --rm \
  -v $(pwd)/.env:/app/.env \ # Use ENV variables and configuration from your file-system
  -v $(pwd)/config:/app/config \
  -v $(pwd)/data:/app/data \
  -v $(pwd)/cache:/app/cache \ # Use your file system to store the vector database
  <your_app_image_name> \
  npm run generate
```

3. Start the app:

```
docker run \
  --rm \
  -v $(pwd)/.env:/app/.env \ # Use ENV variables and configuration from your file-system
  -v $(pwd)/config:/app/config \
  -v $(pwd)/cache:/app/cache \ # Use your file system to store gea vector database
  -p 3000:3000 \
  <your_app_image_name>
```

## Learn More

To learn more about LlamaIndex, take a look at the following resources:

- [LlamaIndex Documentation](https://docs.llamaindex.ai) - learn about LlamaIndex (Python features).
- [LlamaIndexTS Documentation](https://ts.llamaindex.ai) - learn about LlamaIndex (Typescript features).

You can check out [the LlamaIndexTS GitHub repository](https://github.com/run-llama/LlamaIndexTS) - your feedback and contributions are welcome!
