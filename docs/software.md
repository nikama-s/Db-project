# Реалізація інформаційного та програмного забезпечення

В рамках проекту розробляється:

```sql

SET @OLD_UNIQUE_CHECKS=@@UNIQUE_CHECKS, UNIQUE_CHECKS=0;
SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS, FOREIGN_KEY_CHECKS=0;
SET @OLD_SQL_MODE=@@SQL_MODE, SQL_MODE='ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,NO_ZERO_IN_DATE,NO_ZERO_DATE,ERROR_FOR_DIVISION_BY_ZERO,NO_ENGINE_SUBSTITUTION';

-- -----------------------------------------------------
-- Schema databaseLab5
-- -----------------------------------------------------
DROP SCHEMA IF EXISTS `databaseLab5` ;

-- -----------------------------------------------------
-- Schema databaseLab5
-- -----------------------------------------------------
CREATE SCHEMA IF NOT EXISTS `databaseLab5` DEFAULT CHARACTER SET utf8 ;
USE `databaseLab5` ;

-- -----------------------------------------------------
-- Table `databaseLab5`.`User`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `databaseLab5`.`User` ;

CREATE TABLE IF NOT EXISTS `databaseLab5`.`User` (
  `id` INT NOT NULL,
  `name` VARCHAR(45) NULL,
  `surname` VARCHAR(45) NULL,
  `email` VARCHAR(45) NULL,
  `password` CHAR(8) NULL,
  PRIMARY KEY (`id`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `databaseLab5`.`Admin`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `databaseLab5`.`Admin` ;

CREATE TABLE IF NOT EXISTS `databaseLab5`.`Admin` (
  `id` INT NOT NULL,
  `name` VARCHAR(45) NULL,
  `surname` VARCHAR(45) NULL,
  `email` VARCHAR(45) NULL,
  `password` CHAR(8) NULL,
  PRIMARY KEY (`id`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `databaseLab5`.`Permission`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `databaseLab5`.`Permission` ;

CREATE TABLE IF NOT EXISTS `databaseLab5`.`Permission` (
  `name` VARCHAR(45) NULL,
  `description` VARCHAR(255) NULL,
  `id` INT NOT NULL,
  `User_id` INT NOT NULL,
  `Admin_id` INT NOT NULL,
  PRIMARY KEY (`id`, `User_id`, `Admin_id`),
  INDEX `fk_Permission_User_idx` (`User_id` ASC) VISIBLE,
  INDEX `fk_Permission_Admin1_idx` (`Admin_id` ASC) VISIBLE,
  CONSTRAINT `fk_Permission_User`
    FOREIGN KEY (`User_id`)
    REFERENCES `databaseLab5`.`User` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION,
  CONSTRAINT `fk_Permission_Admin1`
    FOREIGN KEY (`Admin_id`)
    REFERENCES `databaseLab5`.`Admin` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `databaseLab5`.`UploadedMedia`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `databaseLab5`.`UploadedMedia` ;

CREATE TABLE IF NOT EXISTS `databaseLab5`.`UploadedMedia` (
  `id` INT NOT NULL,
  `source` INT NULL,
  PRIMARY KEY (`id`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `databaseLab5`.`UploadedMediaSource`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `databaseLab5`.`UploadedMediaSource` ;

CREATE TABLE IF NOT EXISTS `databaseLab5`.`UploadedMediaSource` (
  `id` INT NOT NULL,
  `url` VARCHAR(255) NULL,
  `UploadedMedia_id` INT NOT NULL,
  PRIMARY KEY (`id`, `UploadedMedia_id`),
  INDEX `fk_UploadedMediaSource_UploadedMedia1_idx` (`UploadedMedia_id` ASC) VISIBLE,
  CONSTRAINT `fk_UploadedMediaSource_UploadedMedia1`
    FOREIGN KEY (`UploadedMedia_id`)
    REFERENCES `databaseLab5`.`UploadedMedia` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `databaseLab5`.`Form`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `databaseLab5`.`Form` ;

CREATE TABLE IF NOT EXISTS `databaseLab5`.`Form` (
  `id` INT NOT NULL,
  `name` VARCHAR(45) NULL,
  `description` VARCHAR(45) NULL,
  `content` JSON NULL,
  PRIMARY KEY (`id`))
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `databaseLab5`.`FormResult`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `databaseLab5`.`FormResult` ;

CREATE TABLE IF NOT EXISTS `databaseLab5`.`FormResult` (
  `id` INT NOT NULL,
  `formid` INT NULL,
  `answer` JSON NULL,
  `Form_id` INT NOT NULL,
  PRIMARY KEY (`id`, `Form_id`),
  INDEX `fk_FormResult_Form1_idx` (`Form_id` ASC) VISIBLE,
  CONSTRAINT `fk_FormResult_Form1`
    FOREIGN KEY (`Form_id`)
    REFERENCES `databaseLab5`.`Form` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `databaseLab5`.`Content`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `databaseLab5`.`Content` ;

CREATE TABLE IF NOT EXISTS `databaseLab5`.`Content` (
  `id` INT NOT NULL,
  `type` ENUM("answer") NULL,
  `Form_id` INT NOT NULL,
  PRIMARY KEY (`id`, `Form_id`),
  INDEX `fk_Content_Form1_idx` (`Form_id` ASC) VISIBLE,
  CONSTRAINT `fk_Content_Form1`
    FOREIGN KEY (`Form_id`)
    REFERENCES `databaseLab5`.`Form` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `databaseLab5`.`OpenAnswer`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `databaseLab5`.`OpenAnswer` ;

CREATE TABLE IF NOT EXISTS `databaseLab5`.`OpenAnswer` (
  `id` INT NOT NULL,
  `text` TEXT NULL,
  `Content_id` INT NOT NULL,
  PRIMARY KEY (`id`, `Content_id`),
  INDEX `fk_OpenAnswer_Content1_idx` (`Content_id` ASC) VISIBLE,
  CONSTRAINT `fk_OpenAnswer_Content1`
    FOREIGN KEY (`Content_id`)
    REFERENCES `databaseLab5`.`Content` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `databaseLab5`.`SingleChoise`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `databaseLab5`.`SingleChoise` ;

CREATE TABLE IF NOT EXISTS `databaseLab5`.`SingleChoise` (
  `id` INT NOT NULL,
  `variant` VARCHAR(45) NULL,
  `Content_id` INT NOT NULL,
  PRIMARY KEY (`id`, `Content_id`),
  INDEX `fk_SingleChoise_Content1_idx` (`Content_id` ASC) VISIBLE,
  CONSTRAINT `fk_SingleChoise_Content1`
    FOREIGN KEY (`Content_id`)
    REFERENCES `databaseLab5`.`Content` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


-- -----------------------------------------------------
-- Table `databaseLab5`.`MultiChoise`
-- -----------------------------------------------------
DROP TABLE IF EXISTS `databaseLab5`.`MultiChoise` ;

CREATE TABLE IF NOT EXISTS `databaseLab5`.`MultiChoise` (
  `id` INT NOT NULL,
  `variants` JSON NULL,
  `Content_id` INT NOT NULL,
  PRIMARY KEY (`id`, `Content_id`),
  INDEX `fk_MultiChoise_Content1_idx` (`Content_id` ASC) VISIBLE,
  CONSTRAINT `fk_MultiChoise_Content1`
    FOREIGN KEY (`Content_id`)
    REFERENCES `databaseLab5`.`Content` (`id`)
    ON DELETE NO ACTION
    ON UPDATE NO ACTION)
ENGINE = InnoDB;


SET SQL_MODE=@OLD_SQL_MODE;
SET FOREIGN_KEY_CHECKS=@OLD_FOREIGN_KEY_CHECKS;
SET UNIQUE_CHECKS=@OLD_UNIQUE_CHECKS;

-- -----------------------------------------------------
-- Data for table `databaseLab5`.`User`
-- -----------------------------------------------------
START TRANSACTION;
USE `databaseLab5`;
INSERT INTO `databaseLab5`.`User` (`id`, `name`, `surname`, `email`, `password`) VALUES (1, 'David', 'Krykota', 'a@gmail.com', 'a111');
INSERT INTO `databaseLab5`.`User` (`id`, `name`, `surname`, `email`, `password`) VALUES (2, 'Tymur', 'Naboka', 'b@gmail.com', 'b222');
INSERT INTO `databaseLab5`.`User` (`id`, `name`, `surname`, `email`, `password`) VALUES (3, 'Nika', 'Maslo', 'c@gmail.com', 'c333');

COMMIT;


-- -----------------------------------------------------
-- Data for table `databaseLab5`.`Admin`
-- -----------------------------------------------------
START TRANSACTION;
USE `databaseLab5`;
INSERT INTO `databaseLab5`.`Admin` (`id`, `name`, `surname`, `email`, `password`) VALUES (1, 'admin', 'adminovich', 'admin@gmail.com', 'admin111');

COMMIT;


-- -----------------------------------------------------
-- Data for table `databaseLab5`.`Permission`
-- -----------------------------------------------------
START TRANSACTION;
USE `databaseLab5`;
INSERT INTO `databaseLab5`.`Permission` (`name`, `description`, `id`, `User_id`, `Admin_id`) VALUES ('edit', 'allows to edit form', 1, 1, 1);
INSERT INTO `databaseLab5`.`Permission` (`name`, `description`, `id`, `User_id`, `Admin_id`) VALUES ('answer', 'allows to chose an answer', 2, 1, 1);
INSERT INTO `databaseLab5`.`Permission` (`name`, `description`, `id`, `User_id`, `Admin_id`) VALUES ('check_results', 'allows to check results', 3, 1, 1);

COMMIT;


-- -----------------------------------------------------
-- Data for table `databaseLab5`.`UploadedMedia`
-- -----------------------------------------------------
START TRANSACTION;
USE `databaseLab5`;
INSERT INTO `databaseLab5`.`UploadedMedia` (`id`, `source`) VALUES (1, 123);
INSERT INTO `databaseLab5`.`UploadedMedia` (`id`, `source`) VALUES (2, 456);

COMMIT;


-- -----------------------------------------------------
-- Data for table `databaseLab5`.`UploadedMediaSource`
-- -----------------------------------------------------
START TRANSACTION;
USE `databaseLab5`;
INSERT INTO `databaseLab5`.`UploadedMediaSource` (`id`, `url`, `UploadedMedia_id`) VALUES (1, 'media.com', 1);
INSERT INTO `databaseLab5`.`UploadedMediaSource` (`id`, `url`, `UploadedMedia_id`) VALUES (2, 'othermedia.com', 2);

COMMIT;


-- -----------------------------------------------------
-- Data for table `databaseLab5`.`Form`
-- -----------------------------------------------------
START TRANSACTION;
USE `databaseLab5`;
INSERT INTO `databaseLab5`.`Form` (`id`, `name`, `description`, `content`) VALUES (1, 'wild animals of ukraine', 'choose the best choices for survival', '{\"1\": \"Deers\", \"2\": \"Bears\", \"3\": \"Birds\"}');
INSERT INTO `databaseLab5`.`Form` (`id`, `name`, `description`, `content`) VALUES (2, 'emotions', 'which emotions you experience the most', '{\"1\": \"Emotion1\",\"2\":\"Emotion2\",\"3\":\"Emotion3\"}');

COMMIT;


-- -----------------------------------------------------
-- Data for table `databaseLab5`.`FormResult`
-- -----------------------------------------------------
START TRANSACTION;
USE `databaseLab5`;
INSERT INTO `databaseLab5`.`FormResult` (`id`, `formid`, `answer`, `Form_id`) VALUES (1, 1, '{\"1\":\"a\",\"2\":\"c\",\"3\":\"b\"}', 1);
INSERT INTO `databaseLab5`.`FormResult` (`id`, `formid`, `answer`, `Form_id`) VALUES (2, 2, '{\"1\":\"d\",\"2\":\"a\",\"3\":\"c\",\"4\":\"a\"}', 2);

COMMIT;


-- -----------------------------------------------------
-- Data for table `databaseLab5`.`Content`
-- -----------------------------------------------------
START TRANSACTION;
USE `databaseLab5`;
INSERT INTO `databaseLab5`.`Content` (`id`, `type`, `Form_id`) VALUES (1, 'answer', 1);

COMMIT;


-- -----------------------------------------------------
-- Data for table `databaseLab5`.`OpenAnswer`
-- -----------------------------------------------------
START TRANSACTION;
USE `databaseLab5`;
INSERT INTO `databaseLab5`.`OpenAnswer` (`id`, `text`, `Content_id`) VALUES (1, 'I love wild animals of Ukraine and wish to protect them', 1);

COMMIT;


-- -----------------------------------------------------
-- Data for table `databaseLab5`.`SingleChoise`
-- -----------------------------------------------------
START TRANSACTION;
USE `databaseLab5`;
INSERT INTO `databaseLab5`.`SingleChoise` (`id`, `variant`, `Content_id`) VALUES (1, 'a', 1);
INSERT INTO `databaseLab5`.`SingleChoise` (`id`, `variant`, `Content_id`) VALUES (2, 'sadness', 1);
INSERT INTO `databaseLab5`.`SingleChoise` (`id`, `variant`, `Content_id`) VALUES (3, 'Deer', 1);

COMMIT;


-- -----------------------------------------------------
-- Data for table `databaseLab5`.`MultiChoise`
-- -----------------------------------------------------
START TRANSACTION;
USE `databaseLab5`;
INSERT INTO `databaseLab5`.`MultiChoise` (`id`, `variants`, `Content_id`) VALUES (1, '{\"1\":\"a\",\"2\":\"b\",\"3\":\"c\"}', 1);
INSERT INTO `databaseLab5`.`MultiChoise` (`id`, `variants`, `Content_id`) VALUES (2, '{\"1\":\"d\",\"2\":\"b\",\"3\":\"c\"}', 1);

COMMIT;

```

## REST API для управління даними

### Підключення до бази даних MySql

#### config/connections.js

```javascript
import mysql from "mysql2/promise";
import dotenv from "dotenv";

dotenv.config();

const pool = mysql.createPool({
  host: process.env.DB_HOST,
  user: process.env.DB_USER,
  password: process.env.DB_PASSWORD,
  database: process.env.DB_NAME,
});

export default pool;
```

### Налаштування сервера

#### app.js

```javascript
import express from "express";
import dotenv from "dotenv";

import multiChoiceRoutes from "./routes/multiChoiceRoutes.js";
import singleChoiceRoutes from "./routes/singleChoiceRoutes.js";

import errorHandlingMiddleware from "./middleware/errorMiddleware.js";

dotenv.config();

const app = express();

app.use(express.json());

app.use("/multichoice", multiChoiceRoutes);
app.use("/singlechoice", singleChoiceRoutes);

app.use(errorHandlingMiddleware);

const PORT = process.env.PORT || 3000;
app.listen(PORT, () => {
  console.log(`Server is running on port ${PORT}`);
});
```

### Маршрутизація

#### routes/multiChoiceRoutes.js

```javascript
import express from "express";
import {
  getMultiChoices,
  getMultiChoiceById,
  createMultiChoice,
  updateMultiChoice,
  deleteMultiChoice,
} from "../controllers/multiChoiceController.js";

const router = express.Router();

router.get("/", getMultiChoices);
router.get("/:id", getMultiChoiceById);
router.post("/", createMultiChoice);
router.put("/:id", updateMultiChoice);
router.delete("/:id", deleteMultiChoice);

export default router;
```

#### routes/singleChoiceRoutes.js

```javascript
import express from "express";
import {
  getSingleChoices,
  getSingleChoiceById,
  createSingleChoice,
  updateSingleChoice,
  deleteSingleChoice,
} from "../controllers/singleChoiceController.js";

const router = express.Router();

router.get("/", getSingleChoices);
router.get("/:id", getSingleChoiceById);
router.post("/", createSingleChoice);
router.put("/:id", updateSingleChoice);
router.delete("/:id", deleteSingleChoice);

export default router;
```

### Контролери

#### controllers/multiChoiceController.js

```javascript
import pool from "../config/connection.js";
import QUERIES from "../queries/multiChoiceQueries.js";
import sendResponse from "../utils/sendResponse.js";
import errorFactory from "../utils/errorFactory.js";

const { GET_ALL, GET_BY_ID, CREATE, UPDATE, DELETE } = QUERIES;

export const getMultiChoices = async (req, res, next) => {
  try {
    const [results] = await pool.execute(GET_ALL);
    sendResponse(res, 200, results);
  } catch (err) {
    next(errorFactory.getError(err.message));
  }
};

export const getMultiChoiceById = async (req, res, next) => {
  const { id } = req.params;
  try {
    const [results] = await pool.execute(GET_BY_ID, [id]);
    if (results.length === 0) return next(errorFactory.notFound());
    sendResponse(res, 200, results[0]);
  } catch (err) {
    next(errorFactory.getError(err.message));
  }
};

export const createMultiChoice = async (req, res, next) => {
  const { variants, content_id } = req.body;
  if (!variants || !content_id) return next(errorFactory.missingFields());
  try {
    await pool.execute(CREATE, [JSON.stringify(variants), content_id]);
    sendResponse(res, 201);
  } catch (err) {
    next(errorFactory.createError(err.message));
  }
};

export const updateMultiChoice = async (req, res, next) => {
  const { id } = req.params;
  const { variants, content_id } = req.body;
  if (!variants || !content_id) return next(errorFactory.missingFields());
  try {
    const [result] = await pool.execute(UPDATE, [
      JSON.stringify(variants),
      content_id,
      id,
    ]);
    if (result.affectedRows === 0) return next(errorFactory.notFound());
    sendResponse(res, 200);
  } catch (err) {
    next(errorFactory.updateError(err.message));
  }
};

export const deleteMultiChoice = async (req, res, next) => {
  const { id } = req.params;
  try {
    const [result] = await pool.execute(DELETE, [id]);
    if (result.affectedRows === 0) return next(errorFactory.notFound());
    sendResponse(res, 200);
  } catch (err) {
    next(errorFactory.deleteError(err.message));
  }
};
```

#### controllers/singleChoiceController.js

```javascript
import pool from "../config/connection.js";
import QUERIES from "../queries/singleChoiceQueries.js";
import sendResponse from "../utils/sendResponse.js";
import errorFactory from "../utils/errorFactory.js";

const { GET_ALL, GET_BY_ID, CREATE, UPDATE, DELETE } = QUERIES;

export const getSingleChoices = async (req, res, next) => {
  try {
    const [results] = await pool.execute(GET_ALL);
    sendResponse(res, 200, results);
  } catch (err) {
    next(errorFactory.getError(err.message));
  }
};

export const getSingleChoiceById = async (req, res, next) => {
  const { id } = req.params;
  try {
    const [results] = await pool.execute(GET_BY_ID, [id]);
    if (results.length === 0) return next(errorFactory.notFound());
    sendResponse(res, 200, results[0]);
  } catch (err) {
    next(errorFactory.getError(err.message));
  }
};

export const createSingleChoice = async (req, res, next) => {
  const { variant, content_id } = req.body;
  if (!variant || !content_id) return next(errorFactory.missingFields());
  try {
    await pool.execute(CREATE, [variant, content_id]);
    sendResponse(res, 201);
  } catch (err) {
    next(errorFactory.createError(err.message));
  }
};

export const updateSingleChoice = async (req, res, next) => {
  const { id } = req.params;
  const { variant, content_id } = req.body;
  if (!variant || !content_id) return next(errorFactory.missingFields());
  try {
    const [result] = await pool.execute(UPDATE, [variant, content_id, id]);
    if (result.affectedRows === 0) return next(errorFactory.notFound());
    sendResponse(res, 200);
  } catch (err) {
    next(errorFactory.updateError(err.message));
  }
};

export const deleteSingleChoice = async (req, res, next) => {
  const { id } = req.params;
  try {
    const [result] = await pool.execute(DELETE, [id]);
    if (result.affectedRows === 0) return next(errorFactory.notFound());
    sendResponse(res, 200);
  } catch (err) {
    next(errorFactory.deleteError(err.message));
  }
};
```

### SQL-запити

#### queries/multiChoiceQueries.js

```javascript
const QUERIES = {
  GET_ALL: "SELECT * FROM MultiChoise",
  GET_BY_ID: "SELECT * FROM MultiChoise WHERE id = ?",
  CREATE: "INSERT INTO MultiChoise (variants, content_id) VALUES (?, ?)",
  UPDATE: "UPDATE MultiChoise SET variants = ?, content_id = ? WHERE id = ?",
  DELETE: "DELETE FROM MultiChoise WHERE id = ?",
};

export default QUERIES;
```

#### queries/singleChoiceQueries.js

```javascript
const QUERIES = {
  GET_ALL: "SELECT * FROM SingleChoise",
  GET_BY_ID: "SELECT * FROM SingleChoise WHERE id = ?",
  CREATE: "INSERT INTO SingleChoise (variant, content_id) VALUES (?, ?)",
  UPDATE: "UPDATE SingleChoise SET variant = ?, content_id = ? WHERE id = ?",
  DELETE: "DELETE FROM SingleChoise WHERE id = ?",
};

export default QUERIES;
```

### Відправка відповіді

#### utils/sendResponse.js

```javascript
const sendResponse = (res, statusCode, data = null) => {
  const response = { message: "Success" };
  if (data !== null) {
    response.data = data;
  }
  res.status(statusCode).json(response);
};

export default sendResponse;
```

### Обробка помилок

#### middleware/errorMiddleware.js

```javascript
import HTTP_STATUS_CODES from "../utils/statusCodes.js";

const errorHandlingMiddleware = (err, req, res, next) => {
  const statusCode = err.statusCode || HTTP_STATUS_CODES.INTERNAL_SERVER_ERROR;
  res.status(statusCode).json({
    error: err.message || "Internal Server Error",
    details: err.details || null,
  });
};

export default errorHandlingMiddleware;
```

#### utils/errorFactory.js

```javascript
const formError = (message, statusCode, details = null) => {
  const error = new Error(message);
  error.statusCode = statusCode;
  error.details = details;
  return error;
};

const errorFactory = {
  missingFields: () => formError("Missing fields", 400),
  notFound: () => formError("Resource not found", 404),
  createError: (details) => formError("Create error", 500, details),
  getError: (details) => formError("Get error", 500, details),
  updateError: (details) => formError("Update error", 500, details),
  deleteError: (details) => formError("Delete error", 500, details),
};

export default errorFactory;
```

### Коди статусів HTTP

#### utils/statusCode.js

```javascript
const HTTP_STATUS_CODES = {
  OK: 200,
  CREATED: 201,
  BAD_REQUEST: 400,
  NOT_FOUND: 404,
  INTERNAL_SERVER_ERROR: 500,
};

export default HTTP_STATUS_CODES;
```
