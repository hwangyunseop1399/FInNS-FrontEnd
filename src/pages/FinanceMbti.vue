<template>
  <!--begin::Content-->
  <!-- <div
    class="content fs-6 d-flex flex-column flex-column-fluid"
    id="kt_content"
    style="background-color: white"
  > -->
  <!--begin::Toolbar-->
  <!--begin::Title-->
  <div class="justify-content-center align-items-center text-center bg-title">
    <h1 class="text-gray-900 fw-bold pt-8 mt-9 my-1" style="font-size: xx-large;">금융 MBTI</h1>
    <h2 class="text-gray-700 fw-bold p-4 fs-2">
      소비 내역 분석을 바탕으로 한 나의 MBTI를 확인해 보세요.
    </h2>
  </div>

  <!--end::Title-->
  <div class="toolbar mt-8" id="kt_toolbar">
    <div
      class="container-fluid d-flex flex-stack flex-wrap flex-sm-nowrap justify-content-center align-items-center"
    >
      <!--begin::Info-->
      <div
        class="d-flex flex-column align-items-center justify-content-center flex-wrap"
      ></div>
      <!--end::Info-->
    </div>
  </div>
  <!--end::Toolbar-->
  <div class="parent-container pt-5 pb-5 fs-1">
    <div class="custom-style">
      나의 MBTI
    </div>
  </div>

  <!--begin::Container-->
  <div class="container-xxl">
    <!--begin::Navbar-->
    <!-- <div class="card mb-6"> -->
      <!-- '나의 MBTI' 관련 섹션 -->
  <div class="card-body pt-9 pb-0">
    <!--begin::Details-->
    <div class="d-flex flex-wrap flex-sm-nowrap">
      <!--begin: Pic-->
      <div class="me-7 mb-4" style="margin-left: 110px;">
        <!-- MBTI 프로필 사진을 보여주는 부분에서 mbti_no 사용 -->
        <img :src="getMbtiAvatar(member.mbtiType)" alt="MBTI Profile Picture" />
      </div>
      <!--end::Pic-->

      <!--begin::Info-->
      <div class="flex-grow-1">
        <!--begin::Title-->
        <div class="d-flex justify-content-between align-items-start flex-wrap mb-2">
          <!--begin::User-->
          <div class="d-flex flex-column">
            <!--begin::Name-->
            <div class="d-flex align-items-center mb-2 pt-5">
              <!-- mbti_no 사용 -->
              <p class="text-gray-900 fs-1 fw-bold me-1">
                {{ member.mbtiType }}
                
              </p>
              
            </div>
            <!--end::Name-->
            <!--begin::Info-->
            <div class="d-flex flex-wrap fw-semibold fs-3 mb-4 pe-2">
              <p class="align-items-center text-gray-800 me-5 mb-2">
                {{ member.mbtiDescription }}
              </p>
            </div>
            <!--end::Info-->
          </div>
          <!--end::User-->
        </div>
        <!--end::Title-->
      </div>
      <!--end::Info-->
    </div>
    <!--end::Details-->

    <!-- 조건부 렌더링 (mbti별 다른 p 태그) -->
<div>
  <!-- '먹는게제일좋아형' mbti의 경우 -->
  <p
    v-if="member.mbtiType === '먹는게제일좋아형'"
    class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
  >
    음식에 대한 사랑은 곧 <br />소비로 이어지는 타입! <br />
    맛집 탐방, 고급 요리, <br />신상 메뉴라면 지출도 <br />아깝지 않다!!
  </p>

  <!-- '이것도저것도내꺼형' mbti의 경우 -->
  <p
    v-else-if="member.mbtiType === '이것도저것도내꺼형'"
    class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
  >
    쇼핑몰에 가면 눈에<br /> 보이는 건 전부 내 꺼!<br /> 최신 유행 아이템부터
    <br />희귀템까지 쇼핑 카트는 <br />언제나 가득 차 있다!
  </p>

  <!-- '자기관리마니아형' mbti의 경우 -->
  <p
    v-else-if="member.mbtiType === '자기관리마니아형'"
    class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
  >
    외모와 건강 관리를 최우선으로 생각하는 사람!<br />
    최신 뷰티 제품과 고급 <br />서비스를 위해선 <br />아낌없이 투자하는
    <br />유형이다!!
  </p>

  <!-- '마이아파형' mbti의 경우 -->
  <p
    v-else-if="member.mbtiType === '마이아파형'"
    class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
  >
    건강이 최우선! 병원비와 의료비 지출이 큰 비중을 차지하는 유형이다!!<br />
    정기적인 건강 관리와 <br />치료를 위해 병원과 늘 <br />가까운 사이.
  </p>

  <!-- '통신보안형' mbti의 경우 -->
  <p
    v-else-if="member.mbtiType === '통신보안형'"
    class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
  >
    최신 휴대폰과 초고속 <br />인터넷 없인 못 사는 <br />유형! 
    데이터와 통신비 <br />절약을 위해 소비 습관을 <br />길러보자!!
  </p>

  <!-- '뚜벅초형' mbti의 경우 -->
  <p
    v-else-if="member.mbtiType === '뚜벅초형'"
    class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
  >
    대중교통을 애용하는 <br />뚜벅초형!! 지하철, 버스, 택시 등 교통비가
    주된 <br />지출이며, 경제적이고 <br />빠른 이동을 추구하는 <br />실속파.
  </p>

  <!-- '배낭을매고형' mbti의 경우 -->
  <p
    v-else-if="member.mbtiType === '배낭을매고형'"
    class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
  >
    여행을 위해 사는 당신!!<br />
    비행기 표, 숙소, <br />맛집 탐방까지 여행에 <br />아낌없이 투자하며,
    <br />새로운 모험을 즐기는 <br />여행 마니아.
  </p>

  <!-- '아인슈타인형' mbti의 경우 -->
  <p
    v-else-if="member.mbtiType === '아인슈타인형'"
    class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
  >
    교육과 학습에 아낌없이 투자하는 당신!!<br />
    강의, 학원, 도서, 온라인 강좌 등 지식 습득을 위한 교육비가 가장 큰
    <br />지출 항목.
  </p>

  <!-- '술술들어간다형' mbti의 경우 -->
  <p
    v-else-if="member.mbtiType === '술술들어간다형'"
    class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
  >
    술과 유흥을 즐기는 <br />당신!! 술자리와 유흥비가 가장 큰 지출이며,
    <br />언제나 즐거운 시간을 <br />추구하는 캐릭터.
  </p>

  <!-- 기타 mbti의 경우 -->
  <p
    v-else
    class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
  >
    당신만의 특별한 <br />MBTI를 가진 캐릭터입니다!
    자신의 색깔을 <br />확실하게 표현하는 성격이군요.
  </p>
</div>
  </div>
  <!-- '나의 MBTI' 관련 섹션 끝 -->
    <div class="parent-container pt-5 fs-1">
      <div class="custom-style">
        다른 MBTI
      </div>
    </div>
    <!--begin::Row-->
    <div class="row g-6 g-xl-9" style="width: 800px; margin: auto">
      <!--begin::Col-->
      <div class="col-md-6 col-xl-4">
        <!--begin::Card-->
        <div class="card-container rounded-top">
          <div class="card card-hover">
            <!-- Card Front -->
            <div class="card-front text-center bg-One">
              <!--begin::Card header-->
              <div class="fs-1 fw-bold border-0 pt-7 text-center">
                먹는게제일좋아형
              </div>
              <!--end:: Card header-->
              <!--begin::Card body-->
              <div class="card-body">
                <!-- 이미지 추가 -->
                <div class="image-container">
                  <img src="../../assets/media/avatars/kb_eat.png" />
                </div>
              </div>
            </div>
            <!--end::Card body-->

            <!-- Card Back -->
            <div class="card-back bg-One">
              <div class="card-body p-3">
                <!--begin::Info-->
                <div class="fs-1 fw-bold border-0 pt-4 text-center">
                  먹는게제일좋아형
                </div>
                <p class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 text-center">
                  음식에 대한 사랑은 곧 <br />소비로 이어지는 타입! <br />
                  맛집 탐방, 고급 요리, <br />신상 메뉴라면 지출도 <br />아깝지 않다!!
                </p>
              </div>
            </div>
          </div>
        </div>
        <!--end::Card-->
      </div>
      <!--end::Col-->
      <!--begin::Col-->
      <div class="col-md-6 col-xl-4">
        <!--begin::Card-->
        <div class="card-container">
          <div class="card">
            <!-- Card Front -->
            <div class="card-front text-center bg-Two">
              <!--begin::Card header-->
              <div class="fs-1 fw-bold border-0 pt-7 text-center">
                이것도저것도내꺼형
              </div>
              <!--end:: Card header-->
              <!--begin::Card body-->
              <div class="card-body">
                <!-- 이미지 추가 -->
                <div class="image-container mt-4 text-center">
                  <img src="../../assets/media/avatars/kb_2my.png" />
                </div>
              </div>
            </div>
            <!--end::Card body-->

            <!-- Card Back -->
            <div class="card-back bg-Two">
              <div class="card-body p-3">
                <!--begin::Info-->
                <div class="fs-1 fw-bold border-0 pt-4 text-center">
                  이것도저것도내꺼형
                </div>
                <p
                  class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
                >
                  쇼핑몰에 가면 눈에<br /> 보이는 건 전부 내 꺼!<br /> 최신 유행 아이템부터
                  <br />희귀템까지
                  쇼핑 카트는 언제나 가득 차 있다!
                </p>
              </div>
            </div>
          </div>
        </div>
        <!--end::Card-->
      </div>
      <!--end::Col-->
      <!--begin::Col-->
      <div class="col-md-6 col-xl-4">
        <!--begin::Card-->
        <div class="card-container">
          <div class="card">
            <!-- Card Front -->
            <div class="card-front text-center bg-Three">
              <!--begin::Card header-->
              <div class="fs-1 fw-bold border-0 pt-7 text-center">
                자기관리마니아형
              </div>
              <!--end:: Card header-->
              <!--begin::Card body-->
              <div class="card-body">
                <!-- 이미지 추가 -->
                <div class="image-container mt-4">
                  <img src="../../assets/media/avatars/kb_rabbit.png" />
                </div>
              </div>
            </div>
            <!--end::Card body-->

            <!-- Card Back -->
            <div class="card-back bg-Three">
              <div class="card-body p-3">
                <!--begin::Info-->
                <div class="fs-1 fw-bold border-0 pt-4 text-center">
                  자기관리마니아형
                </div>
                <p
                  class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
                >
                  외모와 건강 관리를 최우선으로 생각하는 사람!<br />
                  최신 뷰티 제품과 고급 <br />서비스를 위해선 <br />아낌없이 투자하는
                  <br />유형이다!!
                </p>
              </div>
            </div>
          </div>
        </div>
        <!--end::Card-->
      </div>
      <!--end::Col-->
      <!--begin::Col-->
      <div class="col-md-6 col-xl-4">
        <!--begin::Card-->
        <div class="card-container">
          <div class="card">
            <!-- Card Front -->
            <div class="card-front text-center bg-four">
              <!--begin::Card header-->
              <div class="fs-1 fw-bold border-0 pt-7 text-center">
                마이아파형
              </div>
              <!--end:: Card header-->
              <!--begin::Card body-->
              <div class="card-body">
                <!-- 이미지 추가 -->
                <div class="image-container mt-4" style="margin-left: -10px;">
                  <img src="../../assets/media/avatars/kb_sick.png" />
                </div>
              </div>
            </div>
            <!--end::Card body-->

            <!-- Card Back -->
            <div class="card-back bg-four">
              <div class="card-body p-3">
                <!--begin::Info-->
                <div class="fs-1 fw-bold border-0 pt-4 text-center">
                  마이아파형
                </div>
                <p
                  class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
                >
                  건강이 최우선! 병원비와 의료비 지출이 큰 비중을 차지하는
                  유형이다!!<br />
                  정기적인 건강 관리와 <br />치료를 위해 병원과 늘 <br />가까운 사이.
                </p>
              </div>
            </div>
          </div>
        </div>
        <!--end::Card-->
      </div>
      <!--end::Col-->
      <!--begin::Col-->
      <div class="col-md-6 col-xl-4">
        <!--begin::Card-->
        <div class="card-container">
          <div class="card">
            <!-- Card Front -->
            <div class="card-front text-center bg-five">
              <!--begin::Card header-->
              <div class="fs-1 fw-bold border-0 pt-7 text-center">
                통신보안형
              </div>
              <!--end:: Card header-->
              <!--begin::Card body-->
              <div class="card-body">
                <!-- 이미지 추가 -->
                <div class="image-container mt-4">
                  <img src="../../assets/media/avatars/kb_phone.png" />
                </div>
              </div>
            </div>
            <!--end::Card body-->

            <!-- Card Back -->
            <div class="card-back bg-five">
              <div class="card-body p-3">
                <!--begin::Info-->
                <div class="fs-1 fw-bold border-0 pt-4 text-center">
                  통신보안형
                </div>
                <p
                  class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
                >
                최신 휴대폰과 초고속 <br />인터넷 없인 못 사는 <br />유형! 
                데이터와 통신비 <br />절약을 위힌 소비 습관을 길러보자!!
                </p>
              </div>
            </div>
          </div>
        </div>
        <!--end::Card-->
      </div>
      <!--end::Col-->
      <!--begin::Col-->
      <div class="col-md-6 col-xl-4">
        <!--begin::Card-->
        <div class="card-container">
          <div class="card">
            <!-- Card Front -->
            <div class="card-front text-center bg-six">
              <!--begin::Card header-->
              <div class="fs-1 fw-bold border-0 pt-7 text-center">뚜벅초형</div>
              <!--end:: Card header-->
              <!--begin::Card body-->
              <div class="card-body">
                <!-- 이미지 추가 -->
                <div class="image-container mt-4">
                  <img src="../../assets/media/avatars/kb_ddubeok.png" />
                </div>
              </div>
            </div>
            <!--end::Card body-->

            <!-- Card Back -->
            <div class="card-back bg-six">
              <div class="card-body p-3">
                <!--begin::Info-->
                <div class="fs-1 fw-bold border-0 pt-4 text-center">
                  뚜벅초형
                </div>
                <p
                  class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
                >
                  대중교통을 애용하는 <br />뚜벅초형!!
                  지하철, 버스, 택시 등 교통비가 주된 <br />지출이며, 경제적이고 <br />빠른
                  이동을 추구하는 <br />실속파.
                </p>
              </div>
            </div>
          </div>
        </div>
        <!--end::Card-->
      </div>
      <!--end::Col-->
      <!--begin::Col-->
      <div class="col-md-6 col-xl-4">
        <!--begin::Card-->
        <div class="card-container">
          <div class="card">
            <!-- Card Front -->
            <div class="card-front text-center bg-seven">
              <!--begin::Card header-->
              <div class="fs-1 fw-bold border-0 pt-7 text-center">
                배낭을매고형
              </div>
              <!--end:: Card header-->
              <!--begin::Card body-->
              <div class="card-body">
                <!-- 이미지 추가 -->
                <div class="image-container mt-4">
                  <img src="../../assets/media/avatars/kb_back.png" />
                </div>
              </div>
            </div>
            <!--end::Card body-->

            <!-- Card Back -->
            <div class="card-back bg-seven">
              <div class="card-body p-3">
                <!--begin::Info-->
                <div class="fs-1 fw-bold border-0 pt-4 text-center">
                  배낭을매고형
                </div>
                <p
                  class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
                >
                  여행을 위해 사는 당신!!<br />
                  비행기 표, 숙소, <br />맛집 탐방까지 여행에  <br />아낌없이 투자하며,
                  <br />새로운 모험을 즐기는  <br />여행 마니아.
                </p>
              </div>
            </div>
          </div>
        </div>
        <!--end::Card-->
      </div>
      <!--end::Col-->
      <!--begin::Col-->
      <div class="col-md-6 col-xl-4">
        <!--begin::Card-->
        <div class="card-container">
          <div class="card">
            <!-- Card Front -->
            <div class="card-front text-center bg-eight">
              <!--begin::Card header-->
              <div class="fs-1 fw-bold border-0 pt-7 text-center">
                아인슈타인형
              </div>
              <!--end:: Card header-->
              <!--begin::Card body-->
              <div class="card-body">
                <!-- 이미지 추가 -->
                <div class="image-container" style="margin-top: -18px; margin-left: -8px;">
                  <img src="../../assets/media/avatars/study.png" height="220px"/>
                </div>
              </div>
            </div>
            <!--end::Card body-->

            <!-- Card Back -->
            <div class="card-back bg-eight">
              <div class="card-body p-3">
                <!--begin::Info-->
                <div class="fs-1 fw-bold border-0 pt-4 text-center">
                  아인슈타인형
                </div>
                <p
                  class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
                >
                  교육과 학습에 아낌없이 투자하는 당신!!<br />
                  강의, 학원, 도서, 온라인 강좌 등 지식 습득을 위한 교육비가
                  가장 큰 <br />지출 항목.
                </p>
              </div>
            </div>
          </div>
        </div>
        <!--end::Card-->
      </div>
      <!--end::Col-->
      <!--begin::Col-->
      <div class="col-md-6 col-xl-4">
        <!--begin::Card-->
        <div class="card-container">
          <div class="card ">
            <!-- Card Front -->
            <div class="card-front text-center bg-nine">
              <!--begin::Card header-->
              <div class="fs-1 fw-bold border-0 pt-7 text-center">
                술술들어간다형
              </div>
              <!--end:: Card header-->
              <!--begin::Card body-->
              <div class="card-body">
                <!-- 이미지 추가 -->
                <div class="image-container mt-4">
                  <img src="../../assets/media/avatars/kb_sul.png" />
                </div>
              </div>
            </div>
            <!--end::Card body-->

            <!-- Card Back -->
            <div class="card-back bg-nine">
              <div class="card-body p-3">
                <!--begin::Info-->
                <div class="fs-1 fw-bold border-0 pt-4 text-center">
                  술술들어간다형
                </div>
                <p
                  class="text-gray-800 fw-semibold fs-2 mt-1 pt-5 mb-7 text-center"
                >
                  술과 유흥을 즐기는 <br />당신!!
                  술자리와 유흥비가 가장 큰 지출이며, <br />언제나 즐거운 시간을
                  <br />추구하는 캐릭터.
                </p>
              </div>
            </div>
          </div>
        </div>
        <!--end::Card-->
      </div>
      <!--end::Col-->
    </div>
    <!--end::Row-->
  </div>
  <!--end::Container-->
  <!-- </div> -->
  <!--end::Content-->
</template>

<script setup>
  import { ref, reactive } from 'vue';
  import { useAuthStore } from '@/stores/auth';
  
  // 인증 스토어
  const auth = useAuthStore();
  
  const member = reactive({
  username: auth.username,
  mbtiType: auth.mbti_no, // mbtiType으로 바로 할당
});
  const isLoading = ref(true);
  
  // Function to get avatar URL based on MBTI type
const getMbtiAvatar = (mbtiType) => {
  switch (mbtiType) {
    case '먹는게제일좋아형':
      return '/assets/media/avatars/kb_eat.png';
    case '이것도저것도내꺼형':
      return '/assets/media/avatars/kb_2my.png';
    case '자기관리마니아형':
      return '/assets/media/avatars/kb_rabbit.png';
    case '마이아파형':
      return '/assets/media/avatars/kb_sick.png';
    case '통신보안형':
      return '/assets/media/avatars/kb_phone.png';
    case '뚜벅초형':
      return '/assets/media/avatars/kb_ddubeok.png';
    case '배낭을매고형':
      return '/assets/media/avatars/kb_back.png';
    case '아인슈타인형':
      return '/assets/media/avatars/study.png';
    case '술술들어간다형':
      return '/assets/media/avatars/kb_sul.png';
    default:
      return '/assets/media/avatars/default_avatar.png';
  }
};

  </script>


<style scoped>
.card-container {
  perspective: 1000px;
}

.card {
  width: 100%;
  height: 300px;
  position: relative;
  transform-style: preserve-3d;
  transition: transform 0.6s;
}

.card-front,
.card-back {
  position: absolute;
  border-radius: 8px;
  width: 100%;
  height: 100%;
  backface-visibility: hidden;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);

}

.card-front {
  background-color: #fff;
}

.card-back {
  background-color: #f8f9fa;
  transform: rotateY(180deg);
}

.card-container:hover .card {
  transform: rotateY(180deg);
}
/* 아래부터 카드들의 background 색상 */
.bg-One {
  background-color: #eff6f9; /* card 첫번째 색상 */
}
.bg-Two {
  background-color: #EFFFEC; /* Powder Blue 색상 */
}
.bg-Three {
  background-color: #FFF2FF; /* Powder Blue 색상 */
}
.bg-four {
  background-color: #f3f2ff; /* Powder Blue 색상 */
}
.bg-five {
  background-color: #fff6f2; /* Powder Blue 색상 */
}
.bg-six {
  background-color: #FFFEED; /* Powder Blue 색상 */
}
.bg-seven {
  background-color: #FFF2FB; /* Powder Blue 색상 */
}
.bg-eight {
  background-color: #ebfdff; /* Powder Blue 색상 */
}
.bg-nine {
  background-color: #f4ebff; /* Powder Blue 색상 */
}

.parent-container {
  display: flex;
  justify-content: center; /* 가로 가운데 정렬 */
  align-items: center; /* 세로 가운데 정렬 */
}

.custom-style {
  color: black;
  font-weight: bold;
  text-decoration: underline;
  text-decoration-color: skyblue;
  text-underline-offset: 6px;
  text-decoration-thickness: 2px;
}

.bg-title {
  background-color: #f0f6f9; /* Powder Blue 색상 */
  height: 180px;
}

</style>
