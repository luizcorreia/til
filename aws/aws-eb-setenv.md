## Upload .env environment variables to elastic beanstalk

Now, if you've got a bunch of environment variables set in a .env file, an easy way to set them en-mass is to just dump them all into the eb setenv command like this...

```bash
eb setenv `cat .env | sed '/^#/ d' | sed '/^$/ d'`
```

This will set them all in one shot and save you spending all night on the aws console page. The sed command remove commented lines and new lines.

[Explain Shell](https://explainshell.com/explain?cmd=cat+.env+%7C+sed+%27%2F%5E%23%2F+d%27+%7C+sed+%27%2F%5E%24%2F+d%27)