- We use "&&" for run multiple commands, and just create one layer for one "RUN" sentence, the image will be smaller

- In "Dockerfile" we have a first approach, in this case we install all, but this is not a good practice because we should install only the essentials

- In "Dockerfile_better" we have an example using multi stage, in the first image with composer, we just install the dependencies, and finally, in the final image we just copy the app with the dependencies installed. In the final image, we don't have composer installed, we just have php but the dependencies are installed

- In "Dockerfile_best" we have the better option, we do the same thing like in "Dockerfile_better" but with some tricks:
    1. In line 4, we just copy composer.json and composer.lock. We don't need all the app for install dependencies, we just need composer.json and composer.lock. So docker will execute the line 4 and 5 ONLY IF composer.json OR composer.lock ARE MODIFIED, OTHERWISE WILL USE THE CACHE.
    2. 