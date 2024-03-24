# Use the official Go image as the base image
FROM golang:latest

# Set the working directory inside the container
WORKDIR /app

# Copy the source code into the container
COPY . .

# Download and install any dependencies using go mod
RUN go mod download

# Build the Go application
RUN go build -o app

# Expose the port on which the application will run
EXPOSE 8080

# Command to run the application when the container starts
CMD ["./app"]
