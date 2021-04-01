# Create interfaces for the reactor:

- REST API for controlling the reactors control rods
	- REST framework: pecan/django/[flask]

# Query the state of control rods:
GET http://localhost:1986/api/controlrods

Returns:
{"rod_state": 55}

# Set control rod state:
POST http://localhost:1986/api/controlrods
{"rod_state": 60}

client side:
curl -v -H "Content-Type: application/json" -X POST http://localhost:1986/api/controlrods -d '{"rod_state":40}'


# Query reactor status:
GET http://localhost:1986/api/reactor_status	(all data about reactor)

# Start reactor:
POST http://localhost:1986/api/start_reactor 	operate=True

# Stop reactor:
POST http://localhost:1986/api/stop_reactor 	False

Push AZ-5 button: stop reduction (100%)
POST http://localhost:1986/api/az-5
