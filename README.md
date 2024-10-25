batch-env
==========

Read environment variables from an in-AWS batch job definition and execute a
command with those variables exported. Think of it like the `env` command, but
it retrieves variable definitions from batch. Helpful for debugging a batch job
locally.

Use like:

```!sh
$ echo "$TZ"

$ batch-env my_test_batch sh -c 'echo "$TZ"'
America/New_York
```

Works well with [swaj](https://github.com/f0rk/swaj) or [eruza](https://github.com/f0rk/eruza):
```!sh
$ swaj --profile dev exec batch-env my_test_app sh -c 'echo "$ENVIRONMENT"'
dev
$ swaj --profile production exec batch-env my_test_app sh -c 'echo "$ENVIRONMENT"'
production
```

Install
=======

```!sh
curl https://raw.githubusercontent.com/f0rk/batch-env/master/batch-env > ~/bin/batch-env
chmod +x ~/bin/batch-env
```
