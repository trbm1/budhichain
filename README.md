# budichain
This project enables building React-based applications on top of the DeSo blockchain using low-code platforms like Budibase, along with modern state management tools like Recoil and React Query. The app focuses on performance, caching, and modularity while integrating DeSo blockchain data seamlessly.

# Features
* DeSo Blockchain Integration: Fetch and manage DeSo blockchain data using React Query for efficient caching and background fetching.

* Low-Code Development: Utilize Budibase for rapid frontend development while integrating custom React components and DeSo API calls.

* State Management: Manage UI and user state with Recoil, and handle remote data with React Query.

* Custom Components: Build dynamic components (e.g., geometric shape generators) that interact with DeSo data.

* Mobile & PWA Support: Optimize for mobile devices and Progressive Web Apps (PWAs) with responsive design and local caching.

* Deployment Flexibility: Deploy the app to platforms like Vercel, Firebase, or custom servers.

# Key Concepts

1️⃣ Fetching and Managing DeSo Blockchain Data
Use React Query to fetch and cache data from DeSo’s API.

Example API: getUsersStateless for fetching user profiles.

Cache API responses to avoid expensive operations:

```
const { data } = useQuery(["user", publicKey], () => fetchUserProfile(publicKey), {
  staleTime: 60000, // Cache for 60 seconds
});
```
Use Recoil for UI state management (e.g., theme, modals, input values).

2️⃣ Using Low-Code Platforms (Budibase) with React & DeSo
Budibase does not natively support DeSo but can integrate via REST APIs.

Use the deso-protocol npm package inside Budibase’s JavaScript blocks.

Add custom NPM components to Budibase for DeSo API calls.

3️⃣ Custom Components & Recoil + React Query Integration
Create custom React components that use Recoil for local state and React Query for DeSo data.

Example: A geometric shape generator that uses DeSo transaction timestamps to dynamically render shapes.

4️⃣ Mobile Performance & PWA Considerations
Test for responsiveness using libraries like Mantine.

Enable PWA support for offline access and device API integration.

Use local storage and caching to reduce blockchain fetches.

5️⃣ Deployment Considerations
Host the app on Vercel, Firebase, or a custom server.

Manage the DeSo node separately if hosting a full node.

Example: Fetching User Data
```
import { useQuery } from "react-query";
import { useRecoilValue } from "recoil";
import { userPublicKeyState } from "./state/atoms";

const fetchUserProfile = async (publicKey) => {
  const response = await fetch(`https://node.deso.org/api/v0/get-users-stateless`, {
    method: "POST",
    headers: { "Content-Type": "application/json" },
    body: JSON.stringify({ PublicKeysBase58Check: [publicKey] }),
  });
  return response.json();
};

const UserProfile = () => {
  const publicKey = useRecoilValue(userPublicKeyState);
  const { data, isLoading } = useQuery(["user", publicKey], () => fetchUserProfile(publicKey));

  if (isLoading) return <div>Loading...</div>;

  return (
    <div>
      <h1>{data.Profiles[0].Username}</h1>
      <p>{data.Profiles[0].Description}</p>
    </div>
  );
};
```

# Roadmap
* Use React Query for DeSo blockchain calls to leverage caching and background fetching.

* Use Recoil for UI and user state management.

* Build Budibase components with external NPM support to integrate DeSo.

* Optimize for mobile & PWA by leveraging caching and responsive design.

# Contributing
Contributions are welcome! Please open an issue or submit a pull request for any improvements or bug fixes.
