# fetch-template
template fetch to replace jquery ajax

```javascript
  fetch('https://some.url.com',{
    method:, //get or post
   headers: {
          "Content-Type": "application/json",
          "Accept": "application/json",
          "X-Requested-With": "XMLHttpRequest",
          "X-CSRF-Token": token, //you can use it on delete with method post or post data without @csrf  token laravel form inside
    },
    body:JSON.stringify({
                'id': id
    }),  //use json.stringfy if you create manual data object
  })
  .then(response => {
    if (response.ok) {
      return Promise.resolve(response);
    }
    else {
      return Promise.reject(new Error('Failed to load')); 
    }
  })
  .then(response => response.json()) // parse response as JSON
  .then(data => {
    // success
  })
  .catch(function(error) {
    console.log(`Error: ${error.message}`);
  });

```
