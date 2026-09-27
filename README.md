function dailyLog184() {
  const inventory = [
    { name: "Keyboard", stock: 12, minimum: 5 },
    { name: "Mouse", stock: 4, minimum: 6 },
    { name: "Monitor", stock: 8, minimum: 4 },
    { name: "Headphones", stock: 3, minimum: 5 }
  ];

  const lowStock = inventory.filter(
    item => item.stock < item.minimum
  );

  const totalItems = inventory.reduce(
    (sum, item) => sum + item.stock,
    0
  );

  const report = {
    date: new Date().toISOString().split("T")[0],
    totalProducts: inventory.length,
    totalStock: totalItems,
    lowStockItems: lowStock.map(item => item.name),
    restockRequired: lowStock.length > 0
  };

  console.log("Daily Inventory Report:", report);
}

dailyLog184();
