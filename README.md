# load-data-to-localStorage

// Code :

const addToLocalStorage=(id)=>{

    let shoppingCart;

    // get the shopping cart-----------------------------------------
    const storedCart=localStorage.getItem('shopping-cart');
    if(storedCart){
        shoppingCart=JSON.parse(storedCart);
    }
    else{
        shoppingCart={};
    }

    // add quantity------------------------------------
    const quantity=shoppingCart[id];
    
    if(quantity){
       console.log('Already exists');
       const newQuantity=parseInt(quantity)+1;
       shoppingCart[id]=newQuantity;
    }
    else{
        shoppingCart[id]=1;
    }

    //set data
    localStorage.setItem('shopping-cart', JSON.stringify(shoppingCart));
}
export {addToLocalStorage}
