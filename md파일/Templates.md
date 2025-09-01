# Django Template system
- 데이터 표현을 제어하면서, 표현과 관련된 부분을 담당
# Django Template Language(DTL)
- Template에서 조건,반복,변수 등의 프로그래밍적 기능을 제공하는 시스템
## DTL Syntax
1. Variable
2. Filters
3. Tags
4. Comments

# 1.Variable
- render 함수의 세번째 인자로 딕셔너리 데이터를 사용
- 딕셔너리 key에 해당하는 문자열이 template에서 사용 가능한 변수명이 됨
- dot(".")을 사용하여 변수 속성에 접근할 수 있음
- {{variable}} - {{variable.attribute}}

# 2.Filters
- 표시할 변수를 수정할 때 사용 (변수 + | + 필터)
- chained(연결)이 가능하며 일부 필터는 인자를 받기도 함
- 약 60개의 built-in template filters를 제공
- {{variable|filter}} - {{name|truncatewords:30}}

# 3.Tages
- 반복 또는 논리를 수행하여 제어 흐름을 만듦
- 일부 태그는 시작과 종료 태그가 필요
- 약 24개의 built-in template tags를 제공
- {% tag %}  -  {% if %} {% endif %}

# 4.Comments
- DTL에서의 주석
- {# name #} , {% comment %}...{% endcomment %}