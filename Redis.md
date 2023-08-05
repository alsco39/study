# Redis

------

## Cache(캐시)

나중에 요청할 결과를 미리 저장해두고 빠르게 서비스를 해주는 것을 말한다.

⇒ 미리 결과를 저장하고 요청이 오면 요청에 대해 DB나 API를 참조하지 않고 Cache를 접근하여 요청을 처리하는 기법이다.

- 캐시는 모든 결과를 캐싱할 필요가 없고 서비스를 할 때 많이 사용되는 부분만 캐싱함으로써 효율을 높일 수 있다.

## Cache 사용구조

![image](https://user-images.githubusercontent.com/103401813/198579053-3ffbc35b-882b-4261-9b3d-a6237f9a6ec7.png)

1. 클라이언트로부터 요청을 받는다.
2. Cache와 작업을 한다.
3. 실제 DB와 작업한다.
4. 다시 Chache와 작업한다.

**Look aside cache**

1. 웹 서버는 클라이언트 요청을 받아서, 데이터가 존재하는 지 캐시를 먼저 확인
2. 캐시에 데이터가 있으면 조회를 하고 없으면 DB에 읽어서 캐시에 저장 후 클라이언트에게 데이터 전달

Write Back

데이터를 전부 캐시에 저장 해놓은 후 특정 시점마다 한 번씩 캐시 내 데이터를 DB에 INSET 한다.

데이터를 일정 기간 동안 유지하고 있어야 하고 유지할 때 Storage 메모리 공간이 서버 장애 상황에서 데이터 손실 우려가 있다.

→ 재생 가능한 데이터나 극단적으로 무거운 데이터에서 많이 사용

------

## Memcached

특징

1. 처리속도가 빠르다.

데이터가 메모리에만 저장되고 속도가 느린 Disk를 거치지 않기 때문이다.

1. 데이터가 메모리에만 저장된다.

프로세스가 죽거나 전력이 공급이 안되면 데이터가 사라진다. → 휘발성

1. 만료일을 지정하여 만료가 되면 자동으로 데이터가 사라진다.

== Cache

1. 저장소 메모리 재사용

만료가 되지 않았더라도 더 이상 데이터를 넣을 메모리가 없다면 LRU 알고리즘에 의해 데이터가 사라진다.

------

## Redis

In-Memory 기반의 키-값 형식의 NoSQL 이다. 별도의 쿼리 작성 없이 데이터를 간단하게 조회 가능하다.

**String, Set, Sorted Set, Hash, List** 자료 구조 지원