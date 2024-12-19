# Dockerfile Wildcard COPY Issue

This repository demonstrates a potential issue when using wildcards in the `COPY` instruction of a Dockerfile.  Improper use of wildcards, specifically when copying `package*.json`, can lead to build failures or inconsistencies.

## Bug Description
The provided Dockerfile uses `COPY package*.json ./` to copy package files. If multiple package-related files (package.json, package-lock.json, etc.) exist, this command might not behave as expected. It may cause errors or omit necessary files during the npm install process, leading to unexpected errors in the Docker image.

## Solution
Instead of using a wildcard, explicitly list the files to copy to ensure only the desired files are included. This improves clarity and reliability.

## How to Reproduce
1. Clone this repository.
2. Build the Docker image with the original Dockerfile (Dockerfile).
3. Observe any errors or unexpected behavior.
4. Build the image with the corrected Dockerfile (DockerfileSolution.txt).
5. Compare the results.
