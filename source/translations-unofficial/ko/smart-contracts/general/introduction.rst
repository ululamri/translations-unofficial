.. Should answer:
    - What is a smart contract
    - Why use a smart contract
    - What are the use cases
    - What are not the use cases

.. _introduction-ko:

===============================
스마트 계약 소개
===============================

스마트 계약은 직접 핵심 프로토콜의 일부가 아닌 동작을 정의하는 데 사용되는 Concordium의 blockchain에
제출 코드의 사용자가 제공 한 조각입니다. 스마트 계약은 미리 정의 된 규칙에 따라 Concordium 네트워크에서 노드에 의해 실행됩니다.
이들의 실행은 완전히 투명하고, 모든 노드는 실행의 결과를 공개적으로 이용 가능한 정보에 근거 것에 동의해야합니다.

스마트 계약은 GTU를 수신, 보유 및 전송할 수 있으며 체인의 일부 측면을 관찰하고 자체 상태를 유지할 수 있습니다.
스마트 계약은 항상 메시지를 보내는 계정과 같은 **외부** 작업에 대한 응답으로 실행됩니다.
실제로 스마트 계약은 종종 온 체인 기능과 오프 체인 기능을 결합한 더 큰 시스템의 작은 부분이 될 것입니다.
오프 체인 기능의 예로는 주식 가격이나 날씨 정보와 같은 실제 데이터를 기반으로 스마트 계약을 호출하는 서버가 있습니다.

스마트 계약이란 무엇입니까?
=============================

스마트 계약은 제 3 자에게 필요한 신뢰를 줄일 수 있습니다,
어떤 경우에는 신뢰할 수있는 타사의 필요성을 제거하고
다른 경우에는 그들의 능력을 감소시켜 그들에게 필요한 신뢰의 양을 감소시킵니다.

스마트 계약은 완전히 투명하게 실행되기 때문에,
노드에 대한 액세스 권한이있는 모든 사람이 확인할 수있는 방식으로,
당사자 간의 합의를 보장하는 데 매우 유용 할 수 있습니다.

.. _auction-ko:

경매 스마트 계약 예
--------------------------------

스마트 계약의 사용 사례는 경매 개최일 수 있습니다.
여기에서 우리는 다른 사람의 다른 입찰을 수락하고 최고 입찰자를 추적하도록 스마트 계약을 프로그래밍합니다.
경매가 끝나면 스마트 계약은 승자 입찰 GTU를 판매자에게 보내고 다른 모든 입찰은 다시 보냅니다.
그런 다음 판매자는 상품을 우승자에게 보내야합니다.

스마트 계약은 경매인의 주요 역할을 대체합니다. 계약 자체는 입찰 부분과 GTU의 온 체인 배포 만 관리합니다.
판매자가 의무를 이행하지 않는 경우 최고 입찰자에게 상환하기위한 논리도 필요할 것입니다.
이는 계약이 판매자가 실제로 의무를 이행했다는 증거 개념을 뒷받침해야 함을 의미합니다.
또는 최고 입찰자가 불만을 제기하는 방법.
스마트 계약은 이러한 실제 문제를 자동으로 해결할 수 없으며 최상의 솔루션은 경매의 세부 사항에 따라 달라질 수 있습니다.

스마트 계약은 *무엇을 위해하지* 인가?
=========================================

스마트 계약은 매우 흥미로운 기술이며 사람들은 여전히이를 활용하는 새로운 방법을 찾고 있습니다.
그러나 스마트 계약이 좋은 해결책이 아닌 경우가 있습니다.

스마트 계약의 주요 장점 중 하나는 코드 실행에 대한 신뢰입니다,
이를 달성하기 위해 블록 체인 네트워크의 많은 노드가 동일한 코드를 실행하고 결과에 대한 동의를 보장해야합니다.
당연히 이것은 일부 클라우드 서비스의 한 노드에서 동일한 코드를 실행하는 것에 비해 비용이 많이 듭니다.

스마트 계약이 무거운 계산에 의존하는 경우, 이 계산을 현명한 계약에서 옮기고 현명한
계약은 계산의 일부 핵심 부분 만 실행합니다. 암호화 기술을 사용하여 다른 부분이 올바르게 실행되도록합니다.

마지막으로, 스마트 계약에는 개인 정보 보호와 **모든 것** 이 없다는 점을 기억하는 것이 중요합니다.
Concordium 네트워크의 모든 사람이 스마트 계약에 액세스 할 수 있습니다.
즉, 스마트 계약에서 민감한 데이터를 처리하기가 어렵습니다.
어떤 경우에는 암호화 도구를 사용하여 데이터를 직접 처리하지 않을 수 있습니다.
오히려 스마트 계약이 실제 데이터를 숨기는 암호화 및 약정과 같은 파생 된 개념으로 작동하도록합니다.

스마트 계약의 수명주기
==============================

스마트 계약은 먼저 :ref:`contract 모듈<contract-module-ko>` 의 일부로 체인에 배포됩니다.
이 후 스마트 계약을 *초기화* 하여 :ref:`스마트 계약 인스턴스 <contract-instances-ko>` 를 얻을 수 있습니다.
마지막으로 스마트 계약 인스턴스는 자체 로직에 따라 반복적으로 업데이트 될 수 있습니다.
