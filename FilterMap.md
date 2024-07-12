# Implement search feature 

```javascript
import { useEffect, useState } from "react";
import "./App.css";

function App() {
  const [allUsers, setAllUsers] = useState([]);
  const [users, setUsers] = useState([]);

  useEffect(() => {
    fetch("https://jsonplaceholder.typicode.com/users")
      .then((response) => response.json())
      .then((json) => {
        setAllUsers(json);
        setUsers(json);
      });
  }, []);

  function searchUser(e) {
    const searchTerm = e.target.value;
    if (searchTerm === "") {
      setUsers(allUsers);
    } else {
      const searchedUsers = allUsers.filter((user) =>
        user.username.toLowerCase().includes(searchTerm.toLowerCase())
      );
      setUsers(searchedUsers);
    }
  }

  return (
    <div>
      <input type="text" placeholder="Search user" onChange={searchUser} />
      <h1>Users</h1>
      <div className="app">
        {users.map((user) => (
          <div className="card" key={user.id}>
            <p>Name: {user.username}</p>
            <p>ZipCode: {user.address.zipcode}</p>
            <p>CompanyName: {user.company.name}</p>
          </div>
        ))}
      </div>
    </div>
  );
}

export default App;

```
