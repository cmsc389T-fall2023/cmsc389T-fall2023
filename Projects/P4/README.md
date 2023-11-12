# Project 6: Git Hooks

For this in-class project, you will create a git hook to send yourself a text 
message through Twilio after each successful commit. You can use the files in 
the [Lecture9 Repo](https://github.com/cmsc389T-spring23/Lecture9) to set up 
your environment. 

Clone and cd into the Lecture9 Repo to get started:

```bash
git clone git@github.com:cmsc389T-spring23/Lecture9.git
cd Lecture9
```

After you have created your post-commit file by following the instructions 
from class, test your post-commit file with either the Docker or Virtual 
Environment set up below.

## Python With Docker

You can create an image by running

```bash
docker build -t project6 .
```

When you want to run this image and connect to its container, just run

```bash
docker run -it project6 bash
```

Once you are inside the container, you can test your hook by doing a quick 
test commit. An example is provided below:

```bash
touch test.txt
git add test.txt
git commit -m "test hook"
```

## Python Without Docker

You can create a virtual environment by running

```bash
bash setup.sh
```

This will create a virtual environment `twilio-env`.
Activate the environment by running

```bash
source twilio-env/bin/activate
```

Once you have activated the environment, you can test your hook by doing a 
quick test commit. An example is provided below:

```bash
touch test.txt
git add test.txt
git commit -m "test hook"
```

## Submission

On Gradescope, submit the following items:

- A screenshot of your post-commit script (feel free to remove any personal 
info)
- A screenshot of the SMS confirmation ID printed to the console with your 
commit message
- A screenshot of the text message you received from Twilio
