import React, { useState, useEffect } from 'react';
import { View, Text, FlatList, Image, TouchableOpacity } from 'react-native';

const App = () => {
  const [products, setProducts] = useState([
    { id: 1, name: 'Product 1', price: 100, image: 'https:                            
    { id: 2, name: 'Product 2', price: 200, image: 'https://example.com/image2.jpg' },
  ]);

  return (
    <View>
      <FlatList
        data={products}
        renderItem={({ item }) => (
          <View>
            <Image source={{ uri: item.image }} />
            <Text>{item.name}</Text>
            <Text>₹{item.price}</Text>
            <TouchableOpacity>
              <Text>Add to Cart</Text>
            </TouchableOpacity>
          </View>
        )}
        keyExtractor={(item) => item.id.toString()}
      />
    </View>
  );
};

export default App;
