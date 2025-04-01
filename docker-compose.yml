services:
  client:
    build: ./client
    ports: 
      - "3000:3000"
    networks:
      - jobnest


  server:
    build: ./server
    ports: 
      - "8080:8080"
    networks:
      - jobnest
    env_file:
      - ./server/.env
    environment:  
      - MONGO_URI=mongodb://mongo:27017/JobNestDevops
      - PORT=8080
    depends_on:
      - mongo


  mongo:
    image: mongo:latest
    ports: 
      - "27017:27017"
    networks:
      - jobnest
    volumes: 
      - mongo_data:/data/db

networks:
  jobnest:
    driver: bridge

volumes:
  mongo_data:
    driver: local
