우선은.. 적고나서 생각해보자.

SRE에 대해서 찾아보다가 알아본것.. 아래와 같이 정리해도 재미있을것 같다는 것이다.

참조 : https://bcho.tistory.com/1325

```

packge google.Devops

/*
    SRE (Site Reliability Engineering)

    개발팀: 개발속도 중요, 주어진 시간내에 새로운 기능 개발
    운영팀: 시스템 안정성 중요, 
    
    사일로 : 개발팀이 무리하게 기능을 배포하게 되면 장애로 이어지고, 이러한 장애로 인하여 서로를 욕하는 상황이 만들어져서 팀이 서로 멀어지게된다. 
    
    그래서 Devops는 이러한 두팀을 한팀에 묶어 놓고 운영하는 문화이자 일종의 운영 철학이다.

    그런데 그러면 운영팀과 개발팀을 묶어놓으면 운영을 하던 사람들은 무엇을 하는가? 요즘은 클라우드가 발전해서 왠만한 부분은 개발자들이 직접 배포하고 운영도 할 수 있지만 시스템이 커지면 여전히 운영의 역할은 필요하다. 
    
    Devops 엔지니어라고 이름을 바꾼 운영팀이 하는 일은 무엇인가?
    > 개발자가 셀프 서비스로 운영할수 있게 플랫폼을 자동화 시킨다.
    >>
    애플리케이션을  빌드하고 유연하게 배포하고, 이를 모니터링할 수 있는 플랫폼이 필요한데, SRE의 역할은 이러한 플랫폼을 개발하고, 이 플랫폼 위에서 개발자들이 스스로 배포,운영을 하는 것이 목표이다. 물론 완벽한 셀프 서비스는 불가능하다. 여전히 큰 장애 처리나 배포등은 SRE 엔지니어가 관여하지만 많은 부분을 개발팀이 스스로 할 수 있도록 점점 그 비중을 줄여 나간다.    
*/

//SRE는 단순히 구글의 운영팀을 지칭하는 것이 아니라, 문화와 운영 프로세스 팀 구조등 모든 개념을 포함한 포괄적인 개념이다. 
class SRE implements Devops{
    private 가용성; 
    private SRE ;

    private 개발팀;
    private 운영팀;
    private 사일로;

    `가용성에 대한 명확한 정의`();
    `가용성 목표 정의`();
    `장애 발생에 대한 계획`();
}

```

기획,관리팀 : 실적을 내기위한 기능과 화려함
개발자 : 요구사항 충족기능, 시간내 완료
관리자 : 리포팅, 리턴, 지시, 많은 화면, 다각적 시각 필요
운영자 : 오류 안나게, 신속한 조치, 원인파악
사용자 : 편리성, 적은 화면, 자기 자신만의 화면



배민에 보이는 요건을 보고 하고 싶은것을 해보자.
> 기준이 되어 줄수도 있다.

개발/인프라 : [배달의민족부문] DevOps 엔지니어 모집
    > SRE, DevOps

개발/서버 : [배민플랫폼실] 서버 개발자 모집
    > JPA외에는 평범한...

개발/서버 : [배달의민족부문] 공통시스템 개발자 모집
    > 인증과 큐잉에 대한 시스템 DevOps

개발/서버 : [배달의민족부문] 검색서비스 개발자 모집    
    > 될수 있으면 하고 싶은.. 요건을 충족해보자.


일종의 Summary
어떤 경험
어떤 생각
최대한 숫자로 표현

---

파이선에 대한 생각 : [포프티비](https://www.youtube.com/watch?v=UsbCQhs3usc&feature=push-lsb&attr_tag=D8Xtu77vzmMauSiL%3A6)에서 말한내용

> 타입체크가 좋다고 하고 하는데, 타입체크는 필요하다. 특히 대규모 프로젝트에서는 말이다.
>> 파이선에서는 넘피가 좋다.
[넘피](https://namu.wiki/w/NumPy)
>>> 개인적으로 쓰는것은 좋다.

텐서플로

SEO(Search Engin Optimatin?:검색엔진 최적화) : 
- 마케터가 주로 한다.
- 90%가 구글
- 한국은 네이버
- SEO를 도와주는 구글 extention이 있다.


---

Iternet Object
> csv비슷한것, xml과 같은 스키마가 있다.

---

WebAssemble : 프론트엔드를 위한.. 자바스크립트를 버리는???

타입스크립트
> 마소에서 주도하고 있다?

---

매니징과 언매니징 프로그램을 알아야하 하는 이유
[가자](https://www.youtube.com/watch?v=ESU2IkFj9VM)
한언어를 파는게 중요하다.
> c를 배워야하나.. c++이나?, 아하하하 
>> 내가 남들과 차이점은 무엇인가?
>>> 언매니징이 중요하다.. 학교때 배우는게 좋다.