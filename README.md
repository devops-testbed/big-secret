# OpenAPI Schema Encoding Repository

This repository demonstrates how to base64 encode an OpenAPI schema and use it as a GitHub secret. The encoded schema can then be used in GitHub Actions workflows.

## What we are doing

1. We are downloading the OpenAPI schema from its source using `curl`.

2. We are encoding the downloaded schema in base64 format. This is necessary because GitHub Secrets cannot store multiline strings, and the schema is a multiline JSON.

3. We are copying the base64 encoded schema to the clipboard. This makes it easy to paste the schema into a GitHub secret.

4. We are creating a GitHub secret and pasting the base64 encoded schema into it. This secret can then be used in GitHub Actions workflows.

## Steps to follow

1. Run the following command in your terminal to download and base64 encode the schema:

    For Unix-like systems:

    ```bash
    curl https://raw.githubusercontent.com/OAI/OpenAPI-Specification/main/schemas/v3.0/schema.json | base64 -w 0 | xclip -selection clipboard

To create the README file in your workspace, you can follow these steps:

1. Open the [`README.md`](command:_github.copilot.openRelativePath?%5B%22README.md%22%5D "README.md") file in your workspace. It seems like it already exists as per your workspace structure.

2. Replace the existing content (if any) with the following:

```markdown
# OpenAPI Schema Encoding Repository

This repository demonstrates how to base64 encode an OpenAPI schema and use it as a GitHub secret. The encoded schema can then be used in GitHub Actions workflows.

## What we are doing

1. We are downloading the OpenAPI schema from its source using `curl`.

2. We are encoding the downloaded schema in base64 format. This is necessary because GitHub Secrets cannot store multiline strings, and the schema is a multiline JSON.

3. We are copying the base64 encoded schema to the clipboard. This makes it easy to paste the schema into a GitHub secret.

4. We are creating a GitHub secret and pasting the base64 encoded schema into it. This secret can then be used in GitHub Actions workflows.

## Steps to follow

1. Run the following command in your terminal to download and base64 encode the schema:

   For Unix-like systems:

   ```bash
   curl https://raw.githubusercontent.com/OAI/OpenAPI-Specification/main/schemas/v3.0/schema.json | base64 | xclip -selection clipboard
   ```

   For Mac:

   ```bash
   curl https://raw.githubusercontent.com/OAI/OpenAPI-Specification/main/schemas/v3.0/schema.json | base64 |  head -c 14000  | pbcopy
   ```

   For Windows PowerShell:

   ```powershell
   Invoke-WebRequest -Uri https://raw.githubusercontent.com/OAI/OpenAPI-Specification/main/schemas/v3.0/schema.json -OutFile schema.json; [Convert]::ToBase64String([IO.File]::ReadAllBytes("schema.json")) | Set-Clipboard
   ```

2. Go to the GitHub repository where you want to add the secret.

3. Click on "Settings" -> "Secrets" -> "New repository secret".

4. Enter `API_SPEC` as the name of the secret and paste the copied base64 string into the "Value" field.

5. Click on "Add secret" to save the secret.

Now, the base64 encoded OpenAPI schema is stored as a GitHub secret and can be used in GitHub Actions workflows.
```

3. Save the [`README.md`](command:_github.copilot.openRelativePath?%5B%22README.md%22%5D "README.md") file.

Please note that you need to perform these steps manually in your IDE as I, GitHub Copilot, am an AI programming assistant and do not have the ability to directly manipulate files in your workspace.