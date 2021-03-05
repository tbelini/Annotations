# Configurações de performance

Note abaixo as configurações para melhorar o desempenho do seu JDeveloper

## Desabilite o build automático
Acesse o menu Tools >> Preferences >> Code Editor >> Save Actions
Remova o item “Build After Save”, clicando no X no canto superior direito.

## Atualize o arquivo $ORACLE_HOME\jdeveloper\ide\bin\ide.conf

As configurações abaixo, em GB, foram direcionadas a um computador com 16GB de RAM.
Para uso de RAM com disponibilidade menor, usar racionamente o Xmx.

### Atualizar no arquivo

```
AddVMOption  -Xms2G
AddVMOption  -Xmx6G
```

## Atualize o arquivo $ORACLE_HOME\jdeveloper\jdev\bin\jdev.conf

### Atualizar no arquivo
```
AddVMOptionHotspot  -XX:MaxPermSize=1G
```

### Adicionar ao final do arquivo
```
#Adiciona monitor no canto inferior, para auxiliar a visualização do uso de RAM pelo JDeveloper
AddVMOption -DMainWindow.MemoryMonitorOn=true

#Adicione as seguintes opções da JVM no final do arquivo
AddVMOption -XX:+UseStringCache
AddVMOption -XX:+OptimizeStringConcat
AddVMOption -XX:+UseCompressedStrings
AddVMOption -XX:+UseCompressedOops
AddVMOption -XX:+AggressiveOpts
AddVMOption -XX:+UseConcMarkSweepGC
AddVMOption -DVFS_ENABLE=true
AddVMOption -Dsun.java2d.ddoffscreen=false
AddVMOption -XX:+UseParNewGC
AddVMOption -XX:+CMSIncrementalMode
AddVMOption -XX:+CMSIncrementalPacing
AddVMOption -XX:CMSIncrementalDutyCycleMin=0
AddVMOption -XX:CMSIncrementalDutyCycle=10
```
