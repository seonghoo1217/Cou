### Member

| 컬럼명            | 데이터 타입       | 제약조건                        | Nullable | 설명          |
|----------------|--------------|-----------------------------|----------|-------------|
| `id`           | BIGINT       | PRIMARY KEY, AUTO_INCREMENT | NOT NULL | 회원 고유 ID    |
| `email`        | VARCHAR(255) | UNIQUE                      | NOT NULL | 회원 이메일      |
| `password`     | VARCHAR(255) |                             | NOT NULL | 회원 비밀번호     |
| `emailConsent` | TINYINT(1)   |                             | NOT NULL | 이메일 수신 동의여부 |

### Cosmetic

| 컬럼명            | 데이터 타입       | 제약조건        | Nullable | 설명       |
|----------------|--------------|-------------|----------|----------|
| `uuid`         | UUID         | PRIMARY KEY | NOT NULL | 상품 고유 ID |
| `cosmeticName` | VARCHAR(255) | UNIQUE      | NOT NULL | 상품 이름    |
| `brand`        | VARCHAR(255) |             | NOT NULL | 상품 브랜드   |
| `price`        | INT          |             |          |          |
| `site_id`      | BIGINT       | FK          |          |          |

### SITE

| 컬럼명        | 데이터 타입       | 제약조건                        | Nullable | 설명     |
|------------|--------------|-----------------------------|----------|--------|
| `id`       | BIGINT       | PRIMARY KEY, AUTO_INCREMENT | NOT NULL | 사이트 ID |
| `siteName` | VARCHAR(255) |                             | NOT NULL | 상품 사이트 |
| `siteUrl`  | VARCHAR(255) |                             |          | 사이트 주소 |

### PRICE_HISTORY

| 컬럼명        | 데이터 타입       | 제약조건                        | Nullable | 설명          |
|------------|--------------|-----------------------------|----------|-------------|
| `id`       | BIGINT       | PRIMARY KEY, AUTO_INCREMENT | NOT NULL | 상품 고유 ID    |
| `price`    | INT          |                             | NOT NULL | 이전 가격       |
| `date`     | DATE         |                             | NOT NULL | 이전 가격 날짜    |
| `siteName` | VARCHAR(255) |                             | NOT NULL | 이메일 수신 동의여부 |
| `siteUrl`  | VARCHAR(255) |                             |          |             |

### WISHLIST

| 컬럼명          | 데이터 타입 | 제약조건                        | Nullable | 설명       |
|--------------|--------|-----------------------------|----------|----------|
| `id`         | BIGINT | PRIMARY KEY, AUTO_INCREMENT | NOT NULL | 위시리스트ID  |
| `memberId`   | BIGINT | FK                          | NOT NULL | 찜한 회원    |
| `cosmeticId` | UUID   | FK                          | NOT NULL | 찜한 상품 ID |