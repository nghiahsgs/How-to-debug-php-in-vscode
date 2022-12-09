# How-to-debug-php-in-vscode
How to debug php in vscode

# Step 1: install php on macos
```
brew update
echo 'eval "$(/opt/homebrew/bin/brew shellenv)"'
```

```
brew tap shivammathur/php
brew install shivammathur/php/php@8.0
```

```
echo 'export PATH="/opt/homebrew/opt/php@8.0/bin:$PATH"' >> ~/.zshrc
echo 'export PATH="/opt/homebrew/opt/php@8.0/sbin:$PATH"' >> ~/.zshrc
export LDFLAGS="-L/opt/homebrew/opt/php@8.0/lib"
export CPPFLAGS="-I/opt/homebrew/opt/php@8.0/include"
```

restart terminal and run
```
php -v

```

# Step 2: Install xdebug
```
pecl install xdebug
```

check xdebug is inserted to php or not ?
```
php -m | grep "xdebug"

```



# Step3: Add config on php.ini on mac os
```
zend_extension="xdebug.so"
xdebug.mode = debug
xdebug.start_with_request = yes
xdebug.client_port=9003
```


# Step4: Open vs code and install extension
```
extension name : php debug
```

Click debug button (left menu of vs code), click create lanch file (port 9003) and enjoy the debugger !
