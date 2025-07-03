```
bitbake_test  
|---- conf                  
    |---- bitbake.conf          
    |---- bblayers.conf
|---- classes                 
    |---- base.bbclass          
|---- mylayer        
    |---- hello.bb             
    |---- conf/             
        |---- layer.conf       
```

- bblayers.conf: Layer list for build process
- layer.conf: Current layer's own path & the path of recipe files whitin the layer
- bitbake.conf: Basic path setting for outputs of each step

### Bitbake parsing
bblayers.conf, layer.conf -> BBPATH -> **bitbake** <br/>
layers.conf -> BBFILES -> **bitbake** <br/>
bitbake.conf -> **bitbake** <br/>

**bitbake** -> hello.bb
