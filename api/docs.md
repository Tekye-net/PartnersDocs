![Logo](https://tekye.net/favicon-32x32.png)


# مستندات تکیه

مستندات همکاری در محتوا برای هیئات


#### آدرس پایه - BaseURI

- https://adminapi.tekye.net


#### پارامترهای اجباری Header

- X-API-KEY
- X-Tenant 

## - دریافت لیست محتواهای ثبت شده
```http
  GET /api/v1/Content/GetContentWithPagination
```

| Parameter | Type     |  Place | Description                |
| :-------- | :------- | :----- |:------------------------- |
| `X-API-KEY` | `string` | `Header` | **Required**. Your API key |
| `X-Tenant` | `string` | `Header` | **Required**. Your Tenant Id |
| `PageNumber` | `integer` | `Params` | **Required**. Page Number  |
| `PageSize` | `integer` | `Params` | **Required**. Size of Content List |
| `Title` | `string` | `Params` |  Part of content Title  |


## - آپلود فایل
برای ذخیره فایل ها  از آدرس زیر استفاده کنید

```http
  POST  https://upload.tekye.net/upload
```
| Parameter | Type     | Place | Description                |
| :-------- | :------- | :-----| :------------------------- |
| `X-API-KEY` | `string` | `Header` | **Required**. Your API key |
| `X-Tenant` | `string` |  `Header` |**Required**. Your Tenant Id |
| `file` | `file` |  `Body` | form-data field with name 'file'  |

## - دریافت دسته‌بندی‌ها
```http
  GET  /api/v1/Category/GetCategoriesDropDownPagination
```

| Parameter | Type     | Place | Description                |
| :-------- | :------- | :-----| :------------------------- |
| `X-API-KEY` | `string` | `Header` | **Required**. Your API key |
| `X-Tenant` | `string` |  `Header` |**Required**. Your Tenant Id |
| `PageNumber` | `integer` | `Params` | **Required**. Page Number  |
| `PageSize` | `integer` | `Params` | **Required**. Size of Content List |
| `CategoryTypeId  ` | `integer` | `Params` | **Required**. Category Type ID |

| Category Type | ID     |
| :-------- | :------- |
| `Event` | `1` |
| `Genre` | `2` |
| `Category` | `3` |
| `Character` | `4` |
| `Place` | `6` |
| `Year` | `7` |

## - دریافت کد مداحان و سخنرانان
```http
  GET  /api/v1/Artist/GetArtistsDropDownPagination
```

| Parameter | Type     | Place | Description                |
| :-------- | :------- | :-----| :------------------------- |
| `X-API-KEY` | `string` | `Header` | **Required**. Your API key |
| `X-Tenant` | `string` |  `Header` |**Required**. Your Tenant Id |
| `PageNumber` | `integer` | `Params` | **Required**. Page Number  |
| `PageSize` | `integer` | `Params` | **Required**. Size of Content List |
| `FullName` | `string` | `Params` | **Optional**. نام مداح یا سخنران |
| `ArtistTypeId` | `number` | `Params` | **Optional**. آیدی مداح یا سخنران |

| Artist Type | ID     |
| :-------- | :------- |
| `مداح` | `1` |
| `سخنران` | `2` |
| `قاری` | `3` |


## - ثبت محتوا

```http
  POST  /api/v1/Partner/AddContent
```
| Parameter | Type     | Place | Description                |
| :-------- | :------- | :-----| :------------------------- |
| `X-API-KEY` | `string` | `Header` | **Required**. Your API key |
| `X-Tenant` | `string` |  `Header` |**Required**. Your Tenant Id |
| `title` | `string` |  `Body` | عنوان محتوا  |
| `mediaFilePath` | `string` |  `Body` | آدرس فایل آپلود شده  |
| `thumbnailFilePath` | `string` |  `Body` | آدرس عکس آپلود شده  |
| `description` | `string` |  `Body` | توضیحات محتوا  |
| `lyrics` | `string` |  `Body` | متن قطعه   |
| `artistsId` | `number[]` |  `Body` | آیدی مداح یا سخنران   |
| `categoriesId` | `number[]` |  `Body` | آیدی دسته بندی   |
| `eventId` | `number[]` |  `Body` | آیدی مناسبت   |
| `genresId` | `number[]` |  `Body` | آیدی سبک   |
| `yearId` | `number` |  `Body` | آیدی سال محتوا   |
| `placeId` | `number` |  `Body` | محل خلق اثر   |
| `tekyeId` | `number` |  `Body` | آیدی تکیه   |
| `tags` | `string[]` |  `Body` | تگ‌های محتوا   |

