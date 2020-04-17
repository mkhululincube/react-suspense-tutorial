# React Suspense

> React suspense is all about delaying loading/fetching of data

<Suspense> let you use wait for anything including data fetching, images and scripts

Suspense enable you components to wait before rendering

##### Suspense example

```` const resource = getProducts();

function Products() {
  return (
    <Suspense fallback={<h1>Loading products...</h1>}>
      <ProfileDetails />
      <Suspense fallback={<h1>Loading products...</h1>}>
        <ProfileTimeline />
      </Suspense>
    </Suspense>
  );
}

function RecentProducts() {
  // Try to read user info, although it might not have loaded yet
  const product = resource.product.read();
  return <h1>{product.name}</h1>;
}

function RelatedProducts() {
  // Try to read products, although they might not have loaded yet
  const products = resource.products.read();
  return (
    <ul>
      {products.map(product => (
        <li key={product.id}>{product.name}</li>
      ))}
    </ul>
  );
} ````

