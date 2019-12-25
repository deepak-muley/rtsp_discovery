Mac:
<pre>
brew install nmap
nmap --script rtsp-url-brute -d -p 554 localhost
</pre>

Alpine:
https://hub.docker.com/r/instrumentisto/nmap
<pre>
docker run --rm -it instrumentisto/nmap -A -T4 scanme.nmap.org
</pre>

My Custom namp RTSP discovery:
<pre>
docker-compose up --build
docker run --rm -it nmap_rtsp_discovery --script rtsp-url-brute -d -p 554 localhost

docker run --rm -it --entrypoint "/usr/bin/nmap" --network host -v $(pwd)/data:/data nmap_rtsp_discovery --script rtsp-url-brute --script-args rtsp-url-brute.urlfile=./rtsp-urls.txt -d -p 554 localhost

docker run --rm -it --entrypoint "/bin/sh" nmap_rtsp_discovery
</pre>

Links:
https://nmap.org/nsedoc/scripts/rtsp-url-brute.html
https://blog.victormendonca.com/2018/02/09/how-to-scan-for-rtsp-urls/
