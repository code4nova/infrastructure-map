## How to setup Ushahidi Environment

### Setup Ushahidi Platform:
1. `git clone https://github.com/ushahidi/platform.git`
2. `cd platform/`
3. `docker-compose build`
4. Run `docker-compose up` Alternatively, you can use `docker-compose up -d` to run it in the background.

### Setup Ushahidi Platform-client
1. `git clone https://github.com/ushahidi/platform-client.git`
2. `cd platform-client`
3. `git checkout develop`
4. `npm run install:all` (If you run into any problems use Node version 12)
5. Next create a `.env` file in the platform-client directory.
   - Inside the `.env` file add `BACKEND_URL=http://127.0.0.1:8080/`. If using a different url for the platform api set it here.
6. To start the local development server run `npm run serve`
7. Once the local dev server loads the client will be available at http://127.0.0.1:3000/

### Using the Platform Pattern Library
1. `git clone https://github.com/ushahidi/platform-pattern-library.git`
2. `cd platform-pattern-library`
3. `npm install`
4. `gulp build`
5. Running `gulp` will start a webserver that shows instructions and examples of the different components used by the platform client.
6. To change CSS and to create HTML templates edit the necessary files in the `assets` directory.
7. Migrating the changes to the `platform-client`:
   - In the `platform-pattern-library` directory run `gulp build`
   - Then copy all files in the `assets` directory
   - Move to the `platform-client` directory and navigate to `legacy/node_modules/ushahidi-platform-pattern-library/` and replace all files inside with the files copied from the `assets` folder.
   - After copying the files over, go back into the `legacy` directory and run `gulp build`.
   - To see your changes run `npm run serve`.
