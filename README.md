# Termux-Service-Registrar

An Interactive CLI Tool For Termux, Which Helps Defining A ServIce To Be Run Using Termux-Services. Written In Bash. 

May Also Work With Systems Using `runit` Init System, Or Similar. Requires Testing For The Same. 

# Usage :- 

```
termux-service-registrar <argument>
```

### Where, `<argument>` Can Be :- 

1. `register` , `--register` , `reg` , `--reg` , `r` , `-r` . 

2. `deregister` , `--deregister` , `dereg` , `--dereg` , `d` , `-d` . 

# Cases :- 

### 1. Normal Daemon Process Registration :- 

Here, 

1A. Any Standard Daemon Software, Which Does Not Detaches Itself From The TTY, Or Allows Running Its Background Running Daemon Process On The Foreground, Can Be Registered Using This Method. 

1B. It Uses `$PREFIX/bin/sh` As A Shebang For Run Script. 

### 2. uDocker - Based Daemon Process Registration :- 

Here, 

2A. Any Standard Daemon Software, Similar To `1A`, But Functional And Executable As A Container, Can Be Registered Using This Method. 

2B. This Method Sets The uDocker As A Service, Rather Than The Container As A Service. 

2C. Setting Container As A Service Is Only Possible, If Appropriate `proot` Command Is Known. 

2D. This Method Only Allows Using The Full uDocker Command. 

2E. Does Not Allow Executing Any Script File, That Runs A uDocker Command. 

2F. The Run Script Must Not Contain Any Line Breaks Like `\` . 

2G. The uDocker Command Must Not End With `&` . 

2H. It Uses `$PREFIX/bin/bash` As A Shebang For Run Script. 

# Recommended Syntax :- 

```
exec <service command> 2>&1
```

# License :- 

GP GNU GPL V3 BAYBEE 🔥🔥🔥🗿

See `License.txt` . 
