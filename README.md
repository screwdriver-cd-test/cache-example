# Build Cache Example

To use build cache in Screwdriver v4, you can specify a top-level setting in your screwdriver.yaml called `cache` that contains file paths from your build that you would like to cache. You can limit access using the pipeline, event, or job scope.

### Example

```
cache:
   event:
       - $SD_SOURCE_DIR/node_modules
   pipeline:
       - ~/.gradle
   job:
       test-job: [/tmp/test]
```

In the above example, we cache the .gradle folder so that subsequent builds in the pipeline can save time on `gradle install`.
