```
mkdir  && cd 
git init
git remote add –f  
git config core.sparsecheckout true
echo some/dir/ >> .git/info/sparse-checkout
echo another/sub/tree >> .git/info/sparse-checkout
git pull  
```
