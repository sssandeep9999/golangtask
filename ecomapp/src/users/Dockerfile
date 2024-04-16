# Stage 1: Build the application
FROM golang:1.16 AS builder

# Set the working directory inside the container
WORKDIR /app

# Copy the Go module files
COPY go.mod go.sum ./

# Download dependencies
RUN go mod download

# Copy the rest of the application source code
COPY . .

# Build the application
RUN CGO_ENABLED=0 GOOS=linux go build -o users-service .

# Stage 2: Run the build binary in a distroless image
FROM gcr.io/distroless/base-debian10

# Copy the binary built in the previous stage
COPY --from=builder /app/users-service /

# Set the entry point
ENTRYPOINT ["/users-service"]

