var http = require("http");

// Cara 1
/* http.createServer(function(req, res) {
	res.writeHead(200, {"Content-Type": "text/plain"});
	res.write("Hello World");	
	res.end();
}).listen(8888);
*/
// Cara 2 - refactoring
/*function onRequest(req, res) {
	console.log("Request received");
	res.writeHead(200, {"Content-Type": "text/plain"});
	res.write("Hello World");
	res.end();
}

http.createServer(onRequest).listen(8888);

console.log("Server has started on 8888");
*/

// Cara 3
var http = require("http");
var url = require("url");

function start(route, handle) {
	function onRequest(req, res) {
		var pathname = url.parse(req.url).pathname;
		console.log("Request for: " + pathname + " received.");
		
		route(handle, pathname, res);
	}	
	
	http.createServer(onRequest).listen(8888);
	console.log("Server has started.");
}

exports.start = start;





