# Wiki Project

This project is a small yet feature-rich application designed to allow users to explore the most read articles, posts of the day, and images of the day on Wikipedia.

The project utilizes React as the frontend framework and NestJS for the backend. Additionally, it employs tools such as Ant Design, React Query, and React Router for managing API requests, state, app routing, and component design.

## How to Set Up

There are two methods for setting up the project:

1. **Using Docker:**

   - Clone this repository and ensure Docker is installed.
   - Run `docker-compose up`. Once the build is complete, navigate to `localhost:3000/feed/en/featured/2024/03/31` for the backend and `localhost:4173` for the frontend.

2. **Manual Setup:**
   - Navigate to the `/back` folder, run `yarn install`, then `yarn start:dev`.
   - Next, go to the frontend folder, run `yarn install`, then `yarn dev`.

For mobile native support, Capacitor is being used. To run the mobile app:

- After completing the previous steps, run `yarn build`, then `npx cap copy`.
- For Android, run `npx cap open android`; for iOS, run `npx cap open ios`.

For running Cypress for e2e tests, execute `npx cypress open`.

## Assumptions and Limitations

- The Wiki API provides extensive data, including the most read articles and more properties which I decided to leverage some of them. Pagination is not supported by the Wiki API, so the project uses a frontend pagination implementation. Implementing infinite scrolling could result in bad practices and complex state management techniques since the API does not support pagination itself and since that does not give you a lot of points I dropped it.
- A translate endpoint is available but it requires an API key and is not cost-free. Additionally, the endpoint or service does not support bulk translation so we could not translate all the articles that come in the Wiki response. The current implementation translates a single article by the article id. Integrating frontend functionality could involve clicking to translate a specific article if API key is we have the API key.
