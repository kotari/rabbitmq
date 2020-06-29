To start rabbitmq on minikube, the following components are installed
1) minikube
2) kubectl
3) kustomize

minikube is started with the following command

minikube start --driver=virtualbox

when tried to start minikube with default driver docker ran into issues in download in images from docker so reverted to virtual box

once the minikube is started run two additional commands to allow port forwarding

1) kubectl port-forward service/rabbitmq 8080:15672   (This would allow to access rabbitmq on browser at http://localhost:8080)

2) kubectl port-forward service/rabbitmq 5672:5672  (This is to submit/process messages to/from the queue)

Followed the following article to setup rpc_client.py and rpc_server.py

https://www.rabbitmq.com/tutorials/tutorial-six-python.html

Created conda environment and pip installed pika 

To start server python server/rpc_server.py

To submit a request python client_rpc_client.py