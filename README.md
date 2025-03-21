# budichain
This project enables building Svelte-based applications on top of the DeSo blockchain using low-code platforms like Budibase, along with modern state management tools like Svelte Stores and TanStack Query. The app focuses on performance, caching, and modularity while integrating DeSo blockchain data seamlessly.

# Features
DeSo Blockchain Integration: Fetch and manage DeSo blockchain data using TanStack Query for efficient caching and background fetching.

* Low-Code Development: Utilize Budibase for rapid frontend development while integrating custom Svelte components and DeSo API calls.

* State Management: Manage UI and user state with Svelte Stores, and handle remote data with TanStack Query.

* Custom Components: Build dynamic components (e.g., geometric shape generators) that interact with DeSo data.

* Mobile & PWA Support: Optimize for mobile devices and Progressive Web Apps (PWAs) with responsive design and local caching.

* Deployment Flexibility: Deploy the app to platforms like Vercel, Firebase, or custom servers.

# Key Concepts
1️⃣ Fetching and Managing DeSo Blockchain Data
Use TanStack Query to fetch and cache data from DeSo’s API. Example API: getUsersStateless for fetching user profiles. Cache API responses to avoid expensive operations.

2️⃣ Using Low-Code Platforms (Budibase) with Svelte & DeSo
Budibase does not natively support DeSo but can integrate via REST APIs. Use the deso-protocol npm package inside Budibase’s JavaScript blocks. Add custom NPM components to Budibase for DeSo API calls.

3️⃣ Custom Components & Svelte Stores + TanStack Query Integration
Create custom Svelte components that use Svelte Stores for local state and TanStack Query for DeSo data. Example: A geometric shape generator that uses DeSo transaction timestamps to dynamically render shapes.

4️⃣ Mobile Performance & PWA Considerations
Test for responsiveness using libraries like Svelte Material UI or Tailwind CSS. Enable PWA support for offline access and device API integration. Use local storage and caching to reduce blockchain fetches.

5️⃣ Deployment Considerations
Host the app on Vercel, Firebase, or a custom server. Manage the DeSo node separately if hosting a full node.

# Roadmap
Use TanStack Query for DeSo blockchain calls to leverage caching and background fetching.

Use Svelte Stores for UI and user state management.

Build Budibase components with external NPM support to integrate DeSo.

Optimize for mobile & PWA by leveraging caching and responsive design.

# Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.
