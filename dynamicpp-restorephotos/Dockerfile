# Use Alpine Linux as the base image
FROM alpine:latest

# Set the working directory
WORKDIR /app

# Install git and curl
RUN apk add --no-cache git bash curl

# Clone the repository
RUN git clone https://github.com/Nutlope/restorePhotos.git .

# Install the necessary packages
RUN echo "http://dl-cdn.alpinelinux.org/alpine/edge/community" >> /etc/apk/repositories
RUN apk update
RUN apk add nodejs npm

# Install Dependencies
RUN npm install

# Create the .env file and set the environment variable
RUN echo "REPLICATE_API_KEY=250218d9f4712cb9ea7e914d11afb4f6675bccbd" > .env

# Expose port 3000
EXPOSE 3000

# Start the application and map port 3000 to 7564 on host
CMD ["npm", "run", "dev"] && ["-p","7564:3000"]
