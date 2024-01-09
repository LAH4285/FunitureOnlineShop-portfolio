### REST API <br>
### 공지사항
#### 1. 글쓰기 <br>
##### 요청 <br>
\- 기본 정보 <br>

|메서드|URL|인증 방식|
|-|-|-|
|POST|8080/board/save|엑세스 토큰|

\- 헤더 <br>

|이름|설명|필수|
|-|-|-|
|Authorization|Authorization: Baer ${access_token}/json<br>사용자 인증 수단, 엑세스 토큰 값|O|

\- 본문 <br>

|이름|타입|설명|필수|
|-|-|-|-|
|title|String|제목|O
|contents|String|내용|O
|createTime|LocalDateTime|작성시간|x
|updateTime|LocalDateTime|수정시간|x
|boardFile|	MultipartFile[]|첨부파일|x
|userId|Long|유저Id|O

#### 2. 수정 <br>
##### 요청 <br>
\- 기본 정보 <br>

|메서드|URL|인증 방식|
|-|-|-|
|POST|8080/board/update|엑세스 토큰|

\- 헤더 <br>

|이름|설명|필수|
|-|-|-|
|Authorization|Authorization: Baer ${access_token}/json<br>사용자 인증 수단, 엑세스 토큰 값|O|

\- 본문 <br>

|이름|타입|설명|필수|
|-|-|-|-|
|id|Long|BoardId|O
|title|String|제목|O
|contents|String|내용|O
|boardFile|	MultipartFile[]|첨부파일|x


#### 3. 삭제 <br>
##### 요청 <br>
\- 기본 정보 <br>

|메서드|URL|인증 방식|
|-|-|-|
|POST|8080/board/delete/{id}|엑세스 토큰|

\- 헤더 <br>

|이름|설명|필수|
|-|-|-|
|Content-type|application/json<br>요청 데이터 타입|O|
|Authorization|Authorization: Baer ${access_token}<br>사용자 인증 수단, 엑세스 토큰 값|O


#### 4. 게시판 페이징 <br>
##### 요청 <br>
\- 기본 정보 <br>

|메서드|URL|인증 방식
|-|-|-|
|get|8080/board/paging|-

\- 헤더 <br>

|이름|설명|필수
|-|-|-|
|Content-type|application/json<br>요청 데이터 타입|O

##### 응답 <br>

\- 본문 <br>

|이름|타입|설명|필수|
|-|-|-|-|
|id|Long|BoardId|O
|title|String|제목|O
|contents|String|내용|O
|createTime|LocalDateTime|작성시간|x
|updateTime|LocalDateTime|수정시간|x
|boardFile|	MultipartFile[]|첨부파일|x

### boardFile

|이름|타입|설명|필수
|-|-|-|-
|id|Long|첨부 파일 id|O
|filePath|String|파일 경로|O
|fileName|String|파일 명|O
|fileType|String|파일 형식|O
|uuid|String|랜덤 키|O
|fileSize|Long|파일 크기|O


### 옵션 <br>
#### 1. 옵션 저장 <br>
##### 요청 <br>
\- 기본 정보 <br>

|메서드|URL|인증 방식
|-|-|-
|POST|8080/options//products/{productId}/save|인증 토큰


\- 헤더 <br>

|이름|설명|필수|
|-|-|-|
|Content-type|application/json<br>요청 데이터 타입|O|
|Authorization|Authorization: Baer ${access_token}<br>사용자 인증 수단, 엑세스 토큰 값|O

\- 본문 <br>

|이름|타입|설명|필수
|-|-|-|-
|Id|Long|옵션Id|O
|optionName|Long|옵션이름|O
|price|Long|가격|O
|stockQuantity|Long|수량|O
|productId|Long|상품Id|O

##### 응답 <br>
\- 본문 <br>

|이름|타입|설명|필수
|-|-|-|-
|optionName|Long|옵션이름|O
|price|Long|가격|O
|stockQuantity|Long|수량|O
|productId|Long|상품Id|O


#### 2. 옵션 검색 <br>
##### 요청 <br>
\- 기본 정보 <br>

|메서드|URL|인증 방식
|-|-|-
|GET|8080/options/products|-


\- 헤더 <br>

|이름|설명|필수|
|-|-|-|
|Content-type|application/json<br>요청 데이터 타입|O|

##### 응답 <br>

\- 본문 <br>

|이름|타입|설명|필수
|-|-|-|-
|Id|Long|옵션Id|O
|optionName|Long|옵션이름|O
|price|Long|가격|O
|stockQuantity|Long|수량|O
|productId|Long|상품Id|O


#### 3. 옵션 수정 <br>
##### 요청 <br>
\- 기본 정보 <br>

|메서드|URL|인증 방식
|-|-|-
|POST|8080/options/update|인증 토큰

\- 헤더 <br>

|이름|설명|필수
|-|-|-
|Content-type|application/json<br>요청 데이터 타입|O
|Authorization|Authorization: Baer ${access_token}<br>사용자 인증 수단, 엑세스 토큰 값|O

##### 응답 <br>
\- 본문 <br>

|이름|타입|설명|필수
|-|-|-|-
|optionName|Long|옵션이름|O
|price|Long|가격|O
|stockQuantity|Long|수량|O
|productId|Long|상품Id|O


#### 4. 옵션 삭제 <br>
##### 요청 <br>
\- 기본 정보 <br>

|메서드|URL|인증 방식
|-|-|-
|POST|8080/options/delete/{id}|인증 토큰

\- 헤더 <br>

|이름|설명|필수
|-|-|-
|Content-type|application/json<br>요청 데이터 타입|O
|Authorization|Authorization: Baer ${access_token}<br>사용자 인증 수단, 엑세스 토큰 값|O
