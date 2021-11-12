# Coding Conventions

## Logging

### Logging

```java
logger.info("--- RedirectUrl : "+transactionRd.getRedirectUrl());
```

```java
logger.info("--- RedirectUrl: {}", transactionRd.getRedirectUrl());
```

### Error

```java
} catch (Exception ex) {
	logger.info("Exception : " + ex.getMessage());
	logger.info("Exception : " + ex);
}
```

```java
} catch (Exception ex) {
	logger.error("ERROR: {}", ex.getMessage());
	ex.printStackTrace();
}
```



## Code Formatter


### Code Formatter Standard

import `Eclipse-Java-EPAY.xml`

### ignore a section of code in eclipse

[Since eclipse 3.5.](https://stackoverflow.com/a/3345289)

- Go to Project Properties > Java Code Style > Formatter > Edit...
- Choose the tab marked "Off/On Tags"
- Include the tags in comments in your source code, like

```java
normal code

/* @formatter:off */
strangely laid out code
/* @formatter:on */

normal code
```
