# Versión corregida del tutorial de AngularJS

Tal como estaba en el repositorio el comando de test end to end no funcionaba
Al ejecutar "npm run protractor", los tests fallaban con un mensaje como el que sigue:

  Message:
    Failed: unknown error: call function result missing 'value'
      (Session info: chrome=68.0.3440.106)
      (Driver info: chromedriver=2.26.436382 (70eb799287ce4c2208441fc057053a5b07ceabac),platform=Linux 4.4.0-133-generic x86_64) (WARNING: The server did not provide any stacktrace information)

En este post se explica que hay que actualizar chromedriver y chrome:
https://github.com/SeleniumHQ/selenium/issues/5674

Así que tuve Tuve que hacer lo siguiente:

Edité estos dos archivos:
node_modules/protractor/node_modules/webdriver-manager/config.json
node_modules/protractor/node_modules/webdriver-manager/built/config.json

Y en los dos agregué esta dependencia:
"chromedriver": "2.41" 

Por último, actualicé Chrome:
sudo apt-get install google-chrome-stable

con estos coambios sí funcionó el comando "npm run protractor"
