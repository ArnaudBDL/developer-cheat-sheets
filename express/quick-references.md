# Express : Quick References

## Minimal server

```javascript
import express from "express";

const app = express();
app.use(express.json());
app.get("/health", (req, res) => res.json({ status: "ok" }));
app.listen(3000);
```

## Router

```javascript
const router = express.Router();
router.get("/:id", controller.show);
router.post("/", controller.create);
app.use("/api/items", router);
```

## Error handler

```javascript
app.use((error, req, res, next) => {
  res.status(error.status ?? 500).json({ message: error.message });
});
```
