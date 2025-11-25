# Zillow56 MCP Server

[English](./README_EN.md) | [简体中文](./README.md) | 繁體中文

## 🚀 使用 EMCP 平台快速體驗

**[EMCP](https://sit-emcp.kaleido.guru)** 是一個強大的 MCP 伺服器管理平台，讓您無需手動配置即可快速使用各種 MCP 伺服器！

### 快速開始：

1. 🌐 造訪 **[EMCP 平台](https://sit-emcp.kaleido.guru)**
2. 📝 註冊並登入帳號
3. 🎯 進入 **MCP 廣場**，瀏覽所有可用的 MCP 伺服器
4. 🔍 搜尋或找到本伺服器（`bach-zillow56`）
5. 🎉 點擊 **「安裝 MCP」** 按鈕
6. ✅ 完成！即可在您的應用中使用

### EMCP 平台優勢：

- ✨ **零配置**：無需手動編輯配置檔案
- 🎨 **視覺化管理**：圖形介面輕鬆管理所有 MCP 伺服器
- 🔐 **安全可靠**：統一管理 API 金鑰和認證資訊
- 🚀 **一鍵安裝**：MCP 廣場提供豐富的伺服器選擇
- 📊 **使用統計**：即時查看服務調用情況

立即造訪 **[EMCP 平台](https://sit-emcp.kaleido.guru)** 開始您的 MCP 之旅！


---

## 簡介

這是一個使用 [FastMCP](https://fastmcp.wiki) 自動生成的 MCP 伺服器，用於存取 Zillow56 API。

- **PyPI 套件名**: `bach-zillow56`
- **版本**: 1.0.0
- **傳輸協定**: stdio


## 安装

### 从 PyPI 安装:

```bash
pip install bach-zillow56
```

### 从源码安装:

```bash
pip install -e .
```

## 运行

### 方式 1: 使用 uvx（推荐，无需安装）

```bash
# 运行（uvx 会自动安装并运行）
uvx --from bach-zillow56 bach_zillow56

# 或指定版本
uvx --from bach-zillow56@latest bach_zillow56
```

### 方式 2: 直接运行（开发模式）

```bash
python server.py
```

### 方式 3: 安装后作为命令运行

```bash
# 安装
pip install bach-zillow56

# 运行（命令名使用下划线）
bach_zillow56
```

## 配置

### API 認證

此 API 需要認證。請設定環境變數:

```bash
export API_KEY="your_api_key_here"
```

### 環境變數

| 變數名 | 說明 | 必需 |
|--------|------|------|
| `API_KEY` | API 金鑰 | 是 |
| `PORT` | 不適用 | 否 |
| `HOST` | 不適用 | 否 |



### 在 Claude Desktop 中使用

编辑 Claude Desktop 配置文件 `claude_desktop_config.json`:


```json
{
  "mcpServers": {
    "zillow56": {
      "command": "python",
      "args": ["E:\path\to\zillow56\server.py"],
      "env": {
        "API_KEY": "your_api_key_here"
      }
    }
  }
}
```

**注意**: 請將 `E:\path\to\zillow56\server.py` 替換為實際的伺服器檔案路徑。


## 可用工具

此服务器提供以下工具:


### `search_polygon_search_for_properties_by_polygon`

Search for filtered properties by polygon coordinates. For a list of properties, you can select the output format (JSON , CSV , XLSX) using the optional \

**端点**: `GET /search_polygon`


**参数**:

- `polygon` (string) *必需*: It is required if the location is empty. Format: lat lng,lat1 lng1,lat2 lng2 34.03959576441558 -118.50636536779786,34.0418716916327 -118.50276047888184,34.042440663894304 -118.49846894445801,34.04201393505594 -118.49417741003418,34.04087598099002 -118.4897142142334,34.03945351693672 -118.48525101843262,34.03788877892429 -118.48095948400879,34.03618175908096 -118.47683961096192,34.034190192514366 -118.47271973791504,34.031629538228394 -118.46962983312989,34.02835747861639 -118.4677415579834,34.02

- `page` (string): Example value: 

- `output` (string): Output format possible values : json (Default value) :Data in a JSON format csv : URL to the generated CSV file xlsx : URL to the generated XLSX (excel) file

- `status` (string): Status type of the properties Default : forSale -forSale -forRent -recentlySold

- `sortSelection` (string): Sorting possible values : days: Newest (Default value), saved: Date Saved, listingstatus: Listing Status, mostrecentchange: Most Recent Change, globalrelevanceex: Homes for You, featured: Verified Source, priced: Price (High to Low), pricea: Price (Low to High), paymentd: Payment (High to Low), paymenta: Payment (Low to High), beds: Bedrooms, baths: Bathrooms, size: Square Feet, lot: Lot Size, zest: Zestimate (High to Low), zesta: Zestimate (Low to High),

- `listing_type` (string): Listing Type possible values : by_agent : By agent (Default value) by_owner_other : By owner & other (for off market properties)

- `isSingleFamily` (string): Example value: 

- `isMultiFamily` (string): Example value: 

- `isApartment` (string): Example value: 

- `isCondo` (string): Example value: 

- `isManufactured` (string): Example value: 

- `isTownhouse` (string): Example value: 

- `isLotLand` (string): Example value: 

- `doz` (string): Days on Zillow (For Sale/Rent listings)/ Sold In Last (Sold listings) Possible values : any: Any, 1: 1 day, 7: 7 days, 14: 14 days, 30: 30 days, 90: 90 days, 6m: 6 months, 12m: 12 months, 24m: 24 months, 36m: 36 months

- `price_min` (string): Example value: 

- `price_max` (string): Example value: 

- `sqft_min` (string): Example value: 

- `sqft_max` (string): Example value: 

- `monthlyPayment_min` (string): Example value: 

- `monthlyPayment_max` (string): Example value: 

- `beds_min` (string): Example value: 

- `beds_max` (string): Example value: 

- `baths_min` (string): Example value: 

- `baths_max` (string): Example value: 

- `hoa_min` (string): Example value: 

- `hoa_max` (string): Example value: 

- `hasPool` (string): Example value: 

- `hasGarage` (string): Example value: 

- `built_min` (string): Example value: 

- `built_max` (string): Example value: 

- `isForSaleByOwner` (string): Example value: 

- `isForSaleByAgent` (string): Example value: 

- `isCityView` (string): Example value: 

- `isWaterfront` (string): Example value: 

- `isPublicSchool` (string): Example value: 

- `isPrivateSchool` (string): Example value: 

- `isMountainView` (string): Example value: 

- `singleStory` (string): Example value: 

- `onlyPriceReduction` (string): Example value: 

- `onlyRentalAcceptsApplications` (string): Example value: 

- `isZillowOwnedOnly` (string): Example value: 

- `hasAirConditioning` (string): Example value: 

- `isMiddleSchool` (string): Example value: 

- `isWaterView` (string): Example value: 

- `onlyRentalIncomeRestricted` (string): Example value: 

- `isComingSoon` (string): Example value: 

- `isForSaleForeclosure` (string): Example value: 

- `onlyWithPhotos` (string): Example value: 

- `onlyRentalCatsAllowed` (string): Example value: 

- `onlyRentalPetsAllowed` (string): Example value: 

- `onlyRentalSmallDogsAllowed` (string): Example value: 

- `onlyRentalLargeDogsAllowed` (string): Example value: 

- `isAuction` (string): Example value: 

- `is3dHome` (string): Example value: 

- `isNewConstruction` (string): Example value: 

- `parkingSpots_min` (string): Example value: 

- `greatSchoolsRating_min` (string): Example value: 

- `isElementarySchool` (string): Example value: 

- `isParkView` (string): Example value: 

- `enableSchools` (string): Example value: 

- `lotSize_max` (string): in sqft

- `keywords` (string): Example value: 



---


### `market_data_rental_market_trends`

Get market rental data of a location by city or ZIP

**端点**: `GET /market_data`


**参数**:

- `location` (string) *必需*: Example value: houston, tx



---


### `market_sale_overview`

This endpoint delivers a comprehensive snapshot and historical trends of the housing market in a given region using metrics aligned with the Zillow Home Value Index (ZHVI) framework

**端点**: `GET /market_sale_overview`


**参数**:

- `location` (string): Example value: houston,tx



---


### `zhvi_range`

This endpoint provides monthly historical data for the Zillow Home Value Index (ZHVI) for a specified region. The ZHVI is a proprietary metric that captures median home values across a wide variety of geographies and housing types, reflecting trends in the real estate market over time.

**端点**: `GET /zhvi_range`


**参数**:

- `location` (string) *必需*: Example value: 11771

- `type` (string): Home type



---


### `search_search_for_properties_by_neighborhood_city_or_zip_code`

Search for filtered properties by neighborhood, city, or ZIP code. PS : To search for an address of a property, use the \

**端点**: `GET /search`


**参数**:

- `location` (string) *必需*: Location can be an address, neighborhood, city, or ZIP code.

- `page` (string): Example value: 

- `output` (string): Output format possible values : json (Default value) :Data in a JSON format csv : URL to the generated CSV file xlsx : URL to the generated XLSX (excel) file

- `status` (string): Status type of the properties Default : forSale -forSale -forRent -recentlySold

- `sortSelection` (string): Sorting possible values : days: Newest (Default value), saved: Date Saved, listingstatus: Listing Status, mostrecentchange: Most Recent Change, globalrelevanceex: Homes for You, featured: Verified Source, priced: Price (High to Low), pricea: Price (Low to High), paymentd: Payment (High to Low), paymenta: Payment (Low to High), beds: Bedrooms, baths: Bathrooms, size: Square Feet, lot: Lot Size, zest: Zestimate (High to Low), zesta: Zestimate (Low to High),

- `listing_type` (string): Listing Type possible values : by_agent : By agent (Default value) by_owner_other : By owner & other (for off market properties)

- `isSingleFamily` (string): Example value: 

- `isMultiFamily` (string): Example value: 

- `isApartment` (string): Example value: 

- `isCondo` (string): Example value: 

- `isManufactured` (string): Example value: 

- `isTownhouse` (string): Example value: 

- `isLotLand` (string): Example value: 

- `doz` (string): Days on Zillow (For Sale/Rent listings)/ Sold In Last (Sold listings) Possible values : any: Any, 1: 1 day, 7: 7 days, 14: 14 days, 30: 30 days, 90: 90 days, 6m: 6 months, 12m: 12 months, 24m: 24 months, 36m: 36 months

- `price_min` (string): Example value: 

- `price_max` (string): Example value: 

- `sqft_min` (string): Example value: 

- `sqft_max` (string): Example value: 

- `monthlyPayment_min` (string): Example value: 

- `monthlyPayment_max` (string): Example value: 

- `beds_min` (string): Example value: 

- `beds_max` (string): Example value: 

- `baths_min` (string): Example value: 

- `baths_max` (string): Example value: 

- `hoa_min` (string): Example value: 

- `hoa_max` (string): Example value: 

- `hasPool` (string): Example value: 

- `hasGarage` (string): Example value: 

- `built_min` (string): Example value: 

- `built_max` (string): Example value: 

- `isForSaleByOwner` (string): Example value: 

- `isForSaleByAgent` (string): Example value: 

- `isCityView` (string): Example value: 

- `isWaterfront` (string): Example value: 

- `isPublicSchool` (string): Example value: 

- `isPrivateSchool` (string): Example value: 

- `isMountainView` (string): Example value: 

- `singleStory` (string): Example value: 

- `onlyPriceReduction` (string): Example value: 

- `onlyRentalAcceptsApplications` (string): Example value: 

- `isZillowOwnedOnly` (string): Example value: 

- `hasAirConditioning` (string): Example value: 

- `isMiddleSchool` (string): Example value: 

- `isWaterView` (string): Example value: 

- `onlyRentalIncomeRestricted` (string): Example value: 

- `isComingSoon` (string): Example value: 

- `isForSaleForeclosure` (string): Example value: 

- `onlyWithPhotos` (string): Example value: 

- `onlyRentalCatsAllowed` (string): Example value: 

- `onlyRentalPetsAllowed` (string): Example value: 

- `onlyRentalSmallDogsAllowed` (string): Example value: 

- `onlyRentalLargeDogsAllowed` (string): Example value: 

- `isAuction` (string): Example value: 

- `is3dHome` (string): Example value: 

- `isNewConstruction` (string): Example value: 

- `parkingSpots_min` (string): Example value: 

- `greatSchoolsRating_min` (string): Example value: 

- `isElementarySchool` (string): Example value: 

- `isParkView` (string): Example value: 

- `enableSchools` (string): Example value: 

- `lotSize_min` (string): in sqft

- `lotSize_max` (string): in sqft

- `keywords` (string): Example value: 



---


### `mortgagerates_mortgage_rates`

Get mortgage rates

**端点**: `GET /mortgage/rates`


**参数**:

- `program` (string) *必需*: The loan program. You can select one or two programs, separated by commas. Available: Fixed30Year, Fixed20Year, Fixed15Year, Fixed10Year, ARM3, ARM5, ARM7, HomeEquity30Year, HomeEquity30YearDueIn15, HomeEquity15Year, HELOC20Year, HELOC15Year, HELOC10Year

- `state` (string): The state abbreviation. AK,AL,AR,AS,AZ,CA,CO,CT,DC,DE,FL,GA, GU,HI,IA,ID,IL,IN,KS,KY,LA,MA,MD,ME,MH, MI,MN,MO,MP,MS,MT,NC,ND,NE, NH,NJ,NM,NV,NY,OH,OK,OR,PA,PR,RI,SC,SD,TN,TX,UT,VA,VI,VT,WA,WI,WV,WY,US

- `refinance` (string): Example value: 

- `loanType` (string): Example value: 

- `loanAmount` (string): Micro < $100,000 SmallConforming $100,000 - $200,000 Conforming > $200,000 SuperConforming Jumbo

- `loanToValue` (string): Normal < 80% High > 80% < 95% VeryHigh >= 95%

- `creditScore` (string): Low < 680 credit score. High > 680 < 740 VeryHigh > 740

- `duration` (string): From 0 to 4000



---


### `buildersdetails_builders_details`

Get details of builders by their builderId (found in `builders/search` results)

**端点**: `GET /builders/details`


**参数**:

- `builderId` (string) *必需*: Example value: 14987



---


### `builderscommunity_cards_builders_community_cards`

Get  community cards of a builder by their builderId (found in `builders/search` results)

**端点**: `GET /builders/community_cards`


**参数**:

- `builderId` (string) *必需*: Example value: 14987

- `regionId` (string): Example value: 

- `page` (string): Example value: 



---


### `buildersreviews_builders_reviews`

Get reviews of a builder by their builderId (found in `builders/search` results)

**端点**: `GET /builders/reviews`


**参数**:

- `builderId` (string) *必需*: Example value: 14987

- `regionId` (string): Example value: 

- `page` (string): Example value: 



---


### `builderssearch_search_for_builders`

Searchfor builders by location or name

**端点**: `GET /builders/search`


**参数**:

- `location` (string): Example value: Houston,Tx

- `name` (string): Example value: 

- `page` (string): Example value: 



---


### `other_professionalsreviews_professionals_reviews`

Get reviews of a professional by their zuid (found in `/other_professionals/details` result)

**端点**: `GET /other_professionals/reviews`


**参数**:

- `zuid` (string) *必需*: Example value: X1-ZU1328lo3ng72mh_5xifh

- `page` (string): Example value: 

- `size` (string): Example value: 



---


### `other_professionalsdetails_professionals_details`

Get details of a professional by username (found in `/other_professionals/search` results)

**端点**: `GET /other_professionals/details`


**参数**:

- `username` (string) *必需*: Example value: InnerLoopHomes



---


### `other_professionalssearch_search_for_professionals`

Search for professoinals (property managers, inspectors,photographers,home_improvement,etc) by location or name

**端点**: `GET /other_professionals/search`


**参数**:

- `location` (string): Example value: Houston,tx

- `type` (string) *必需*: Example value: 

- `name` (string): Example value: 

- `page` (string): Example value: 



---


### `walk_transit_bike_score_walk_transit_and_bike_score`

Get Walk, Transit and Bike Score of a property by zpid

**端点**: `GET /walk_transit_bike_score`


**参数**:

- `zpid` (string): The zpid can be extracted from the searching endpoints (/search , /search_url…), or from a property's URL.

- `url` (string): Property details URL - eg :https://www.zillow.com/homedetails/15626-Laurel-Heights-Dr-Houston-TX-77084/28253016_zpid/



---


### `schools_nearby_schools`

Nearby schools of a property by ZPID

**端点**: `GET /schools`


**参数**:

- `zpid` (string): The zpid can be extracted from the searching endpoints (/search , /search_url…), or from a property's URL.

- `url` (string): Property details URL - eg :https://www.zillow.com/homedetails/15626-Laurel-Heights-Dr-Houston-TX-77084/28253016_zpid/



---


### `photos_photos_of_a_property`

Returns a property's photos with different sizes and types.

**端点**: `GET /photos`


**参数**:

- `zpid` (string): The zpid can be extracted from the searching endpoints (/search , /search_url…), or from a property's URL.

- `url` (string): Property details URL - eg :https://www.zillow.com/homedetails/15626-Laurel-Heights-Dr-Houston-TX-77084/28253016_zpid/



---


### `property_deprecated`

Get a property's details by its zpid

**端点**: `GET /property`


**参数**:

- `zpid` (string): The zpid can be extracted from the searching endpoints (/search , /search_url…), or from a property's URL.

- `url` (string): Property details URL - eg :https://www.zillow.com/homedetails/15626-Laurel-Heights-Dr-Houston-TX-77084/28253016_zpid/



---


### `propertyv2_property_details_by_zpid`

Get a property's details by its zpid

**端点**: `GET /propertyV2`


**参数**:

- `zpid` (string): The zpid can be extracted from the searching endpoints (/search , /search_url…), or from a property's URL.

- `url` (string): Property details URL - eg :https://www.zillow.com/homedetails/15626-Laurel-Heights-Dr-Houston-TX-77084/28253016_zpid/



---


### `lenderreviews`

Get lender reviews

**端点**: `GET /lender/reviews`


**参数**:

- `screenName` (string) *必需*: Example value: mortgagecapitalpartners

- `page` (string): Example value: 



---


### `lenderdetails`

Get lender details

**端点**: `GET /lender/details`


**参数**:

- `screenName` (string) *必需*: Example value: mortgagecapitalpartners



---


### `lendersearch`

Search for Lenders

**端点**: `GET /lender/search`


**参数**:

- `location` (string) *必需*: City, State or Zip. Only lenders licensed in the state will be displayed.

- `lenderName` (string): Example value: 

- `page` (string): Example value: 



---


### `similar_rent_properties_similar_for_rent_properties`

List of similar for rent properties by Zpid or URL or address

**端点**: `GET /similar_rent_properties`


**参数**:

- `zpid` (string): The zpid can be extracted from the searching endpoints (/search , /search_url...), or from a property's URL.

- `url` (string): Property details URL - eg :https://www.zillow.com/homedetails/15626-Laurel-Heights-Dr-Houston-TX-77084/28253016_zpid/

- `address` (string): Example value: 



---


### `search_coordinates_search_for_properties_by_coordinates`

Search for filtered properties by coordinates. You can select the output format (JSON , CSV , XLSX) using the optional \

**端点**: `GET /search_coordinates`


**参数**:

- `lat` (string) *必需*: Latitude

- `long` (string) *必需*: Longitude

- `page` (string): Example value: 

- `status` (string): Status type of the properties Default : forSale -forSale -forRent -recentlySold

- `output` (string): Output format possible values : json (Default value) :Data in a JSON format csv : URL to the generated CSV file xlsx : URL to the generated XLSX (excel) file

- `sort` (string): Sorting possible values : priorityscore: Default, saved: Date Saved, listingstatus: Listing Status, mostrecentchange: Most Recent Change, globalrelevanceex: Homes for You, featured: Verified Source, priced: Price (High to Low), pricea: Price (Low to High), paymentd: Payment (High to Low), paymenta: Payment (Low to High), days: Newest, beds: Bedrooms, baths: Bathrooms, size: Square Feet, lot: Lot Size, zest: Zestimate (High to Low), zesta: Zestimate (Low to High),

- `listing_type` (string): Listing Type possible values : By agent (Default value) By owner & other (for off market properties)

- `isSingleFamily` (string): Example value: 

- `isMultiFamily` (string): Example value: 

- `isApartment` (string): Example value: 

- `isCondo` (string): Example value: 

- `isManufactured` (string): Example value: 

- `isTownhouse` (string): Example value: 

- `isLotLand` (string): Example value: 

- `doz` (string): Days on Zillow possible values : any: Any, 1: 1 day, 7: 7 days, 14: 14 days, 30: 30 days, 90: 90 days, 6m: 6 months, 12m: 12 months, 24m: 24 months, 36m: 36 months

- `price_min` (string): Example value: 

- `price_max` (string): Example value: 

- `sqft_min` (string): Example value: 

- `sqft_max` (string): Example value: 

- `monthlyPayment_min` (string): Example value: 

- `monthlyPayment_max` (string): Example value: 

- `beds_min` (string): Example value: 

- `beds_max` (string): Example value: 

- `baths_min` (string): Example value: 

- `baths_max` (string): Example value: 

- `hoa_min` (string): Example value: 

- `hoa_max` (string): Example value: 

- `hasPool` (string): Example value: 

- `hasGarage` (string): Example value: 

- `built_min` (string): Example value: 

- `built_max` (string): Example value: 

- `isForSaleByOwner` (string): Example value: 

- `isForSaleByAgent` (string): Example value: 

- `isCityView` (string): Example value: 

- `isWaterfront` (string): Example value: 

- `isPublicSchool` (string): Example value: 

- `isPrivateSchool` (string): Example value: 

- `isMountainView` (string): Example value: 

- `singleStory` (string): Example value: 

- `onlyPriceReduction` (string): Example value: 

- `onlyRentalAcceptsApplications` (string): Example value: 

- `isZillowOwnedOnly` (string): Example value: 

- `hasAirConditioning` (string): Example value: 

- `isMiddleSchool` (string): Example value: 

- `isWaterView` (string): Example value: 

- `onlyRentalIncomeRestricted` (string): Example value: 

- `isComingSoon` (string): Example value: 

- `isForSaleForeclosure` (string): Example value: 

- `onlyWithPhotos` (string): Example value: 

- `onlyRentalCatsAllowed` (string): Example value: 

- `onlyRentalPetsAllowed` (string): Example value: 

- `onlyRentalSmallDogsAllowed` (string): Example value: 

- `onlyRentalLargeDogsAllowed` (string): Example value: 

- `isAuction` (string): Example value: 

- `is3dHome` (string): Example value: 

- `isNewConstruction` (string): Example value: 

- `greatSchoolsRating_min` (string): Example value: 

- `isElementarySchool` (string): Example value: 

- `isParkView` (string): Example value: 

- `enableSchools` (string): Example value: 

- `keywords` (string): Example value: 



---


### `search_url_list_of_properties_by_url`

Get a list of properties by providing the zillow search results URL You can select the output format (JSON , CSV , XLSX) using the optional \

**端点**: `GET /search_url`


**参数**:

- `url` (string) *必需*: Example value: https://www.zillow.com/homes/for_sale/2_p/?searchQueryState=%7B%22pagination%22%3A%7B%22currentPage%22%3A2%7D%2C%22mapBounds%22%3A%7B%22west%22%3A-112.39143704189931%2C%22east%22%3A-110.78468655361806%2C%22south%22%3A32.79032628812945%2C%22north%22%3A33.7227901388417%7D%2C%22isMapVisible%22%3Atrue%2C%22filterState%22%3A%7B%22con%22%3A%7B%22value%22%3Afalse%7D%2C%22apa%22%3A%7B%22value%22%3Afalse%7D%2C%22mf%22%3A%7B%22value%22%3Afalse%7D%2C%22ah%22%3A%7B%22value%22%3Atrue%7D%2C%22sort%22%3A%7B%22value%22%3A%22globalrelevanceex%22%7D%2C%22land%22%3A%7B%22value%22%3Afalse%7D%2C%22manu%22%3A%7B%22value%22%3Afalse%7D%2C%22apco%22%3A%7B%22value%22%3Afalse%7D%7D%2C%22isListVisible%22%3Atrue%7D

- `page` (string): Example value: 3

- `output` (string): Output format possible values : json (Default value) :Data in a JSON format csv : URL to the generated CSV file xlsx : URL to the generated XLSX (excel) file

- `listing_type` (string): Listing Type possible values : By agent (Default value) By owner & other (for off market properties)



---


### `search_mls_search_by_mls`

Search for properties by their MLS ID.

**端点**: `GET /search_mls`


**参数**:

- `mls` (string) *必需*: Example value: SR25078433



---


### `agent_details_by_username`

Get agent's details by username(contact infos, active listings and reviews etc). PS : username is the profile link  Example :  username :  Pardee-Properties for https://www.zillow.com/profile/Pardee-Properties/

**端点**: `GET /agent`


**参数**:

- `username` (string) *必需*: Example value: Pardee-Properties



---


### `agents_rental_listings`

Get agent's rental listings by zuid

**端点**: `GET /agent_rental_listings`


**参数**:

- `zuid` (string) *必需*: Example value: X1-ZUz0nmomozy2o9_9bpwk

- `page` (string): Example value: 



---


### `agent_reviews`

Get agent reviews by the agent's zuid

**端点**: `GET /agent_reviews`


**参数**:

- `zuid` (string) *必需*: Example value: X1-ZUz0nmomozy2o9_9bpwk

- `page` (string): Example value: 



---


### `agents_active_listings`

Get agent's active listings by zuid

**端点**: `GET /agent_active_listings`


**参数**:

- `zuid` (string) *必需*: Example value: X1-ZUz0nmomozy2o9_9bpwk

- `page` (string): Example value: 



---


### `search_for_agents`

Search for agents by location and name

**端点**: `GET /search_agents`


**参数**:

- `location` (string) *必需*: Example value: houston, tx

- `name` (string): Example value: 

- `page` (string): Example value: 

- `specialty` (string): Example value: 

- `language` (string): Example value: 



---


### `agents_past_sales`

Get agent's past sales by zuid

**端点**: `GET /agent_past_sales`


**参数**:

- `zuid` (string) *必需*: The zuid can be extracted from the agent's details \"/agent\"

- `page` (string): Example value: 



---


### `similar_sold_properties_similar_sold_properties`

List of similar sold properties by Zpid or URL or address

**端点**: `GET /similar_sold_properties`


**参数**:

- `zpid` (string): The zpid can be extracted from the searching endpoints (/search , /search_url...), or from a property's URL.

- `url` (string): Property details URL - eg :https://www.zillow.com/homedetails/15626-Laurel-Heights-Dr-Houston-TX-77084/28253016_zpid/

- `address` (string): Example value: 



---


### `similar_properties_similar_for_sale_properties`

List of similar for sale properties by Zpid or URL or address

**端点**: `GET /similar_properties`


**参数**:

- `zpid` (string): The zpid can be extracted from the searching endpoints (/search , /search_url...), or from a property's URL.

- `url` (string): Property details URL - eg :https://www.zillow.com/homedetails/15626-Laurel-Heights-Dr-Houston-TX-77084/28253016_zpid/

- `address` (string): Example value: 



---


### `price_tax_history_price_and_tax_history`

Price and Tax history of a property by ZPID

**端点**: `GET /price_tax_history`


**参数**:

- `zpid` (string): The zpid can be extracted from the searching endpoints (/search , /search_url…), or from a property's URL.

- `url` (string): Property details URL - eg :https://www.zillow.com/homedetails/15626-Laurel-Heights-Dr-Houston-TX-77084/28253016_zpid/



---


### `rent_estimate_rent_zestimate`

Returns a property's rent zestimate and it's comparable properties in the same area.

**端点**: `GET /rent_estimate`


**参数**:

- `address` (string) *必需*: Example value: 1545 Yale St, Santa Monica, CA 90404

- `activeTypes` (string): SimilarFloorPlans filter: Possible values: any (Default) active (Active Rentals) inactive (Inactive Rentals)

- `activatedDays` (string): [SIMILARFLOORPLANS] Filter for Active Rentals within X days: Possible values: any (Default) 30 (Within 30 days) 15 (Within 15 days) 7 (Within 7 days)

- `deactivatedDays` (string): [SIMILARFLOORPLANS] Filter for inactive rentals within X days: Possible values: 30 (Within 30 days (max)) 15 (Within 15 days) 7 (Within 7 days)

- `distanceInMiles` (string): [SIMILARFLOORPLANS] Filter for distance in Miles: Possible values: any 1 2 3 4 5

- `propertyTypes` (string): [SIMILARFLOORPLANS] Filter for Property Types: (To choose multiple values separate with comma eg : house,condo) Possible values: any (Default) apartment house townhouse condo

- `bedrooms` (string): [SIMILARFLOORPLANS] Filter for number of bedrooms: (To choose multiple values separate with comma eg : 0,1,2) Possible values: 0 1 2 3 4plus

- `pets` (string): [SIMILARFLOORPLANS] Filter for Pets: (To choose multiple values separate with comma eg : dogs,cats) Possible values: any (Default) dogs cats

- `laundry` (string): [SIMILARFLOORPLANS] Filter for Laundry: (To choose multiple values separate with comma eg : inUnit,shared) Possible values: any (Default) inUnit shared

- `amenities` (string): [SIMILARFLOORPLANS] Filter for amenities: (To choose multiple values separate with comma eg : cooling,parking) Possible values: any (Default) cooling heating parking



---


### `zestimate_history_zestimate_history`

Zestimate history by zpid

**端点**: `GET /zestimate_history`


**参数**:

- `zpid` (string): The zpid can be extracted from the searching endpoints (/search , /search_url…), or from a property's URL.

- `url` (string): Property details URL - eg :https://www.zillow.com/homedetails/15626-Laurel-Heights-Dr-Houston-TX-77084/28253016_zpid/



---


### `search_address_search_for_a_property_by_address`

Search for a property by address.

**端点**: `GET /search_address`


**参数**:

- `address` (string) *必需*: Example value: 1161 Natchez Dr College Station Texas 77845



---



## 技术栈

- **FastMCP**: 快速、Pythonic 的 MCP 服务器框架
- **传输协议**: stdio
- **HTTP 客户端**: httpx

## 开发

此伺服器由 [API-to-MCP](https://github.com/BACH-AI-Tools/api-to-mcp) 工具自動生成。

版本: 1.0.0
