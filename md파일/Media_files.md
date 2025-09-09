# Media Files
- 사용자가 웹에서 업로드하는 정적 파일

# ImageField()
- 이미지 업로에드에 사용하는 모델 필드
- 이미지 객체가 직접 DB에 저장되는것이 아닌 **이미지 파일의 경로**문자열이 저장됨

# 미디어 파일을 제공하기 전 준비사항
1. settings.py에 MEDIA_ROOT, MEDIA_URL 설정
2. 작성한 MEDIA_ROOT와 MEDIA_URL에 대한 URL 지정

# MEDIA_ROOT
- 미디어 파일들이 위치하는 디렉토리의 절대 경로
![alt text](image-55.png)

# MEDIA_URL
- MEDIA_ROOT에서 제공되는 미디어 파일에 대한 주소를 생성(STATIC_URL과 동일한 역할)
![alt text](image-56.png)

# MEDIA_ROOT와 MEDIA_URL에 대한 URL 지정
- 업로드 된 파일의 URL == settings.MEDIA_URL
- MEDIA_URL을 통해 참조하는 파일의 실제 위치 == settings.MEDIA_ROOT
![alt text](image-57.png)

# 이미지 업로드 (1/6)
- blank=True 속성을 작성해 빈 문자열이 저장될 수 있도록 제약 조건 설정
- 게시글 작성 시 이미지 업로드 없이도 작성 할 수 있도록 하기 위함
![alt text](image-58.png)

# 이미지 업로드 (2/6)
- migration 진행
![alt text](image-59.png)

# 이미지 업로드 (3/6)
- form 요소의 enctype 속성 추가
![alt text](image-60.png)

# 이미지 업로드 (4/6)
- ModelForm의 2번째 인자로 요청 받은 파일 데이터 작성
    - ModelForm의 상위 클래스 BaseModelForm의 생성자 함수의 2번째 위치 인자로 파일을 받도록 설정되어있음
![alt text](image-61.png)

# 이미지 업로드 (5/6)
- 이미지 업로드 input 확인
![alt text](image-62.png)

# 이미지 업로드 (6/6)
- 이미지 업로드 결과 확인
![alt text](image-63.png)

# 업로드 이미지 제공하기 (1/3)
- 'url'속성을 통해 업로드 파일의 경로 값을 얻을 수 있음
- article.image.url
    - 업로드 파일의 경로
- article.image
    - 업로드 파일의 파일 이름
![alt text](image-64.png)

# 업로드 이미지 제공하기 (2/3)
- 업로드 이미지 출력 확인 및 MEDIA_URL 확인
![alt text](image-65.png)

# 업로드 이미지 제공하기 (3/3)
- 이미지를 업로드하지 않은 게시물은 detail 템플릿을 렌더링 할 수 없음
- 이미지 데이터가 있는 경우만 이미지를 출력할 수 있도록 처리하기
![alt text](image-66.png)

# 업로드 이미지 수정 (1/2)
- 수정 페이지 form 요소에 enctype 속성 추가
![alt text](image-67.png)

# 업로드 이미지 수정 (2/2)
- update view 함수에서 업로드 파일에 대한 추가 코드 작성
![alt text](image-68.png)

# 참고
## 'upload_to' argument
- ImageField()의 upload_to 속성을 사용해 다양한 추가 경로 설정
![alt text](image-69.png)

## BaseModelForm
# request.FILES가 두번째 위치 인자인 이유
- ModelForm의 상위 클래스 BaseModelForm의 생성자 함수 키워드 인자 참고
![alt text](image-70.png)