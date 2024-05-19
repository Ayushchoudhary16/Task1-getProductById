# Task1-getProductById

const getProductById=async (req,res)=>{
   console.log(req.params);
   const productId = req.params.Id;
    try{
        const product=await Product.findOne({_id: productId});
        console.log(product);
        return res.json({data: product});
    }catch(err){
        return res.json({error : err });
    };
};


 productRoutes.jsx

const express=require("express");
const { getProductById } = require("../../Controllers/Products/productControllers");

const router = express.Router();

router.get("/single-product-by-id/:Id", getProductById);

module.exports=router;
