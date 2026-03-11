const express = require("express");
const auth = require("../middleware/auth");

const router = express.Router();

// Public Route
router.get("/public", (req, res) => {

    res.json({
        message: "This is a public route"
    });
});

// Protected Route
router.get("/profile", auth, (req, res) => {

    res.json({
        message: "Welcome to protected profile route"
    });
});

module.exports = router;
