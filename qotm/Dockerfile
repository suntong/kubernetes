FROM golang:alpine AS builder

# Copy the code from the host and compile it
#WORKDIR ./
COPY . ./
RUN CGO_ENABLED=0 GOOS=linux go build -a -installsuffix nocgo -o /app .

FROM scratch
COPY --from=builder /app ./
ENTRYPOINT ["./app"]
