![PavWeb2](https://user-images.githubusercontent.com/51343959/58841379-986b4180-8637-11e9-9dd2-219979601ac8.PNG)

# PavLogger

This currently provides a easy to use sqlite and postgres database commands.  If you install SQLCypher, the library can also handle the encryption of the database.

The file needs to be compiled with Cython.

## Installation 
Run the following to install:

```python
pip install pav_logger
```

## Usage
Optional:
    log_name:
        Provides a way to specify another log file name:
        Default: debug and exception
    show_backtrace:
        Provides a way to specify to show the backtrace of an message
        Default:
            Debug: False
            Error: True
    log_severity:
        Provides a way to specify a number for the log for SQLite database
        Default:
            Debug: 0
            Error: 4
    line_divider:
        Provides a way to change the dividing line between messages.
        Default:
            '#'

```python
import pav_logger

pav_logger = pav_logger.PavLogger()
pav_logger.log_path = "<Location Folder Path>"
pav_logger.debug('This is a debug message.')

try:
    raise ValueError('There is an error')
except Exception as error:
    pav_logger.error(error)

pav_logger.log_to_database = True
pav_logger.debug('This is a debug message.')

try:
    raise ValueError('There is an error')
except Exception as error:
    pav_logger.error(error)
            
```