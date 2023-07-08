
    const addToLocalStorage=(id)=>{
    let shoppingCart={};

    // get the shopping cart-----------------------------------------
    const storedCart=localStorage.getItem('shopping-cart');
    if(storedCart){
        shoppingCart=JSON.parse(storedCart);
    }

    // add quantity------------------------------------
    const quantity=shoppingCart[id];
    
    if(quantity){
    //    console.log('Already exists');
       const newQuantity=quantity+1;
       shoppingCart[id]=newQuantity;
    }
    else{
        shoppingCart[id]=1;
    }

    //set data
    localStorage.setItem('shopping-cart', JSON.stringify(shoppingCart));
    
    }

    //   ---------------------------Remove----------------------------------------
    const removeFromLocalStorage=(id)=>{
    const storedCart=localStorage.getItem('shopping-cart');
    if(storedCart){
        const shoppingCart=JSON.parse(storedCart);
        if(id in shoppingCart){
            delete shoppingCart[id];
            localStorage.setItem('shopping-cart', JSON.stringify(shoppingCart));
          }
       }
    }

    //   ---------------------------Delete all----------------------------------------
    const deleteShoppingCart=()=>{
    localStorage.removeItem('shopping-cart');
    }
    
    export {addToLocalStorage, removeFromLocalStorage, deleteShoppingCart}
