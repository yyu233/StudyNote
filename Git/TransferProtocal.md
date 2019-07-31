## The Dumb Protocol ##

If you’re setting up a repository to be served read-only over HTTP, the dumb protocol is likely what will be used. This protocol is called “dumb” because it requires no Git-specific code on the server side during the transport process; the fetch process is a series of HTTP GET requests, where the client can assume the layout of the Git repository on the server.   

``` git clone ``` pulls down the ``` info/refs ``` file from remote repo, and this file is written by ``` update-server-info ``` command. Then pulls down HEAD reference, next the commit object, then the tree object.  

## The Smart Protocol ##

The dumb protocol is simple but a bit inefficient, and it can’t handle writing of data from the client to the server. The smart protocol is a more common method of transferring data, but it requires a process on the remote end that is intelligent about Git – it can read local data, figure out what the client has and needs, and generate a custom packfile for it. There are two sets of processes for transferring data: a pair for uploading data and a pair for downloading data.   

Uploading Data    
To upload data to a remote process, Git uses the send-pack and receive-pack processes. The send-pack process runs on the client and connects to a receive-pack process on the remote side.    

Downloading Data    
When you download data, the fetch-pack and upload-pack processes are involved. The client initiates a fetch-pack process that connects to an upload-pack process on the remote side to negotiate what data will be transferred down.   
