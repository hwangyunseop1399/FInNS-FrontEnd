<template>
    <div class="col-lg-8">
        <!--begin::Posts-->
        <div class="mb-10" id="kt_social_feeds_posts">
            <!--begin::Post 1-->
            <!--begin::Card-->
            <div class="card card-flush mb-10">
                <!--begin::Card header-->
                <div class="card-header pt-9">
                    <!--begin::Author-->
                    <div class="d-flex align-items-center">
                        <!--begin::Avatar-->
                        <div class="symbol symbol-50px me-5">
                            <img src="/assets/media/avatars/300-4.jpg" class="" alt="" />
                        </div>
                        <!--end::Avatar-->
                        <!--begin::Info-->
                        <div class="flex-grow-1">
                            <!--begin::Name-->
                            <a href="profile/spending"
                                class="text-gray-800 text-hover-primary fs-4 fw-bold">Yujin_1219</a>
                            <!--end::Name-->
                            <!--begin::Date-->
                            <span class="text-gray-500 fw-semibold d-block">09월 24일 15:30</span>
                            <!--end::Date-->
                        </div>
                        <!--end::Info-->

                        <!-- 모달 트리거 버튼 (display: none; - JS를 통해 제어) -->
                        <button class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#kt_modal_offer_a_deal"
                            style="display: none" ref="modalTrigger"></button>

                        <!--begin::Menu-->
                        <div class="me-0">
                            <button class="btn btn-sm btn-icon btn-bg-light btn-active-color-primary"
                                data-kt-menu-trigger="click" ref="menuButton">
                                <i class="ki-solid ki-dots-horizontal fs-2x me-1"></i>
                            </button>
                            <!--begin::Menu 3-->
                            <div class="menu menu-sub menu-sub-dropdown menu-column menu-rounded menu-gray-800 menu-state-bg-light-primary fw-semibold w-200px py-3"
                                data-kt-menu="true">
                                <!-- 메뉴 항목들 -->
                                <div class="menu-item px-3">
                                    <!-- 프로필 수정 버튼 -->
                                    <router-link to="/postDetails" class="menu-link px-3">
                                        게시물 상세
                                    </router-link>
                                </div>
                            </div>
                            <!--end::Menu 3-->
                        </div>
                        <!--end::Menu-->
                    </div>
                    <!--end::Author-->
                </div>
                <!--end::Card header-->
                <!--begin::Card body-->
                <div class="card-body">
                    <!--begin::Post content-->
                    <!--장소 표시 아이콘-->
                    <div>
                        <span class="svg-icon svg-icon-primary svg-icon-2hx"><svg width="24" height="24"
                                viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path opacity="0.3"
                                    d="M18.0624 15.3453L13.1624 20.7453C12.5624 21.4453 11.5624 21.4453 10.9624 20.7453L6.06242 15.3453C4.56242 13.6453 3.76242 11.4453 4.06242 8.94534C4.56242 5.34534 7.46242 2.44534 11.0624 2.04534C15.8624 1.54534 19.9624 5.24534 19.9624 9.94534C20.0624 12.0453 19.2624 13.9453 18.0624 15.3453Z"
                                    fill="currentColor" />
                                <path
                                    d="M12.0624 13.0453C13.7193 13.0453 15.0624 11.7022 15.0624 10.0453C15.0624 8.38849 13.7193 7.04535 12.0624 7.04535C10.4056 7.04535 9.06241 8.38849 9.06241 10.0453C9.06241 11.7022 10.4056 13.0453 12.0624 13.0453Z"
                                    fill="currentColor" />
                            </svg>

                        </span>
                        <!--장소-->
                        <span class="fs-6 fw-bold text-gray-700 mb-5 ms-2">상구네 솥뚜껑 삼겹살</span>
                    </div>
                    <div class="pt-2 pb-3">
                        <!--카드 아이콘-->
                        <span class="svg-icon svg-icon-dark svg-icon-2hx"><svg width="24" height="24"
                                viewBox="0 0 24 24" fill="none" xmlns="http://www.w3.org/2000/svg">
                                <path d="M22 7H2V11H22V7Z" fill="currentColor" />
                                <path opacity="0.3"
                                    d="M21 19H3C2.4 19 2 18.6 2 18V6C2 5.4 2.4 5 3 5H21C21.6 5 22 5.4 22 6V18C22 18.6 21.6 19 21 19ZM14 14C14 13.4 13.6 13 13 13H5C4.4 13 4 13.4 4 14C4 14.6 4.4 15 5 15H13C13.6 15 14 14.6 14 14ZM16 15.5C16 16.3 16.7 17 17.5 17H18.5C19.3 17 20 16.3 20 15.5C20 14.7 19.3 14 18.5 14H17.5C16.7 14 16 14.7 16 15.5Z"
                                    fill="currentColor" />
                            </svg>
                        </span>
                        <!--가격-->
                        <span class="fs-6 fw-bold text-gray-700 mb-5 ms-2">120,000원</span>
                    </div>
                    <!--end::Post content-->
                    <!--begin:: 게시물 사진-->
                    <Carousel v-if="images.length > 0">
                        <Slide v-for="(image, index) in images" :key="index">
                            <img :src="image" alt="Image Slide" class="carousel-image" />
                        </Slide>

                        <template #addons>
                            <Navigation />
                            <Pagination />
                        </template>
                    </Carousel>
                    <div class="pt-2 pb-4">

                        <!--가격 카테고리-->
                        <span class="fw-bold p-3" style="background-color: #F1F7FF; border-radius: 5px;">
                            <img :src="category[0].icon" alt="icon" style="height: 26px; width: 26px;" />
                            {{ category[0].name }}</span>
                        <span class="fs-6 fw-bold text-gray-700 mb-5 ms-2">에 소비했어요</span>
                    </div>
                    <!--end:: 게시물-->
                    <!--begin::Info-->
                    <div class="mb-6">
                        <!--begin::Separator-->
                        <div class="separator separator-solid"></div>
                        <!--end::Separator-->
                        <!--begin::Nav-->
                        <ul class="nav py-3">

                            <!--댓글보기 버튼-->
                            <li class="nav-item">
                                <a class="nav-link btn btn-sm btn-color-gray-600 btn-active-light-muted fw-bold px-4 me-1 collapsible active"
                                    data-bs-toggle="collapse" href="#kt_social_feeds_comments_1">
                                    <i class="ki-duotone ki-message-text-2 fs-2 me-1">
                                        <span class="path1"></span>
                                        <span class="path2"></span>
                                        <span class="path3"></span>
                                    </i>댓글보기</a>
                            </li>


                            <!--좋은소비 버튼-->
                            <li class="nav-item">
                                <button class="btn btn-sm"
                                    :style="{ backgroundColor: goodisActive ? '#F1F7FF' : '#FFFFFF' }"
                                    @click="goodtoggleActive(), badisActive = false" style="height : 32px;">
                                    <i class="ki-duotone ki-like text-primary fs-2 me-1">
                                        <span class="path1"></span>
                                        <span class="path2"></span>
                                    </i>
                                    <span class="text-primary fw-bold">좋은소비</span>
                                </button>
                            </li>

                            <!--이돈이면 버튼-->
                            <li class="nav-item">
                                <button class="btn btn-sm"
                                    :style="{ backgroundColor: badisActive ? '#FFEFEF' : '#FFFFFF' }"
                                    @click="badtoggleActive(), goodisActive = false" style="height : 32px;">
                                    <i class="ki-duotone ki-dislike text-danger fs-2 me-1">
                                        <span class="path1"></span>
                                        <span class="path2"></span>
                                    </i>
                                    <span class="text-danger fw-bold">이돈이면...</span>
                                </button>
                            </li>
                        </ul>
                        <!--end::Nav-->
                        <!--begin::Separator-->
                        <div class="separator separator-solid mb-1"></div>
                        <!--end::Separator-->
                        <!--begin::댓글-->
                        <div class="collapse show" id="kt_social_feeds_comments_1">
                            <!--begin::Comment-->
                            <div class="d-flex pt-6">
                                <!--begin::Avatar-->
                                <div class="symbol symbol-45px me-5">
                                    <img src="/assets/media/avatars/300-13.jpg" alt="" />
                                </div>
                                <!--end::Avatar-->
                                <!--begin::Wrapper-->
                                <div class="d-flex flex-column flex-row-fluid">
                                    <!--begin::Info-->
                                    <div class="d-flex align-items-center flex-wrap mb-0">
                                        <!--begin::Name-->
                                        <a href="#" class="text-gray-800 text-hover-primary fw-bold me-6">Mr.
                                            Anderson</a>
                                        <!--end::Name-->

                                    </div>
                                    <!--end::Info-->
                                    <!--begin::Text-->
                                    <span class="text-gray-800 fs-7 fw-normal pt-1">맛있는 삼겹살을 드셨네요! 근데 과소비 하신건
                                        아닌지....</span>
                                    <!--end::Text-->
                                </div>
                                <!--end::Wrapper-->
                            </div>
                            <!--end::Comment-->

                        </div>
                        <!--end::Collapse-->
                    </div>
                    <!--end::Info-->
                    <!--begin::Comment form-->
                    <div class="d-flex align-items-center">
                        <!--begin::Author-->
                        <div class="symbol symbol-35px me-3">
                            <img src="/assets/media/avatars/300-3.jpg" alt="" />
                        </div>
                        <!--end::Author-->
                        <!--begin::Input group-->
                        <div class="position-relative w-100">
                            <!--댓글 작성-->
                            <textarea type="text" class="form-control form-control-solid border ps-5" rows="1"
                                name="search" value="" data-kt-autosize="true" placeholder="댓글을 작성하세요."></textarea>

                        </div>
                    </div>
                </div>
            </div>
            <!--end::Card-->
            <!--end::Post 1-->
        </div>
    </div>
</template>
<script setup>
import { ref, onMounted, nextTick } from 'vue';
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Navigation, Pagination } from 'vue3-carousel';
import { useRouter } from 'vue-router';
// 모달 트리거를 위한 ref
const modalTrigger = ref(null);
// 메뉴를 위한 ref
const menuButton = ref(null);
onMounted(async () => {
    // DOM이 렌더링된 후 초기화
    await nextTick();

    // 모달 트리거
    if (modalTrigger.value) {
        modalTrigger.value.click();
    }

    // 메뉴 초기화 (만약 `KTMenu`를 사용 중이라면)
    if (window.KTMenu && menuButton.value) {
        window.KTMenu.createInstances();
    }

    setDataList();
});

const router = useRouter();

const goToPostViewPage = () => {
    router.push('/postView'); // PostViewPage로 이동
};

const goodisActive = ref(false)
const badisActive = ref(false)

const goodtoggleActive = () => {
    goodisActive.value = !goodisActive.value
}
const badtoggleActive = () => {
    badisActive.value = !badisActive.value
}

const category = [
    { name: '식비&카페', icon: '/assets/media/category/meal.png' },
    { name: '쇼핑', icon: '/assets/media/category/shopping.png' },
    { name: '미용', icon: '/assets/media/category/alcohol.png' },
    { name: '의료', icon: '/assets/media/category/alcohol.png' },
    { name: '통신', icon: '/assets/media/category/alcohol.png' },
    { name: '교통', icon: '/assets/media/category/alcohol.png' },
    { name: '문화&여행', icon: '/assets/media/category/alcohol.png' },
    { name: '교육', icon: '/assets/media/category/alcohol.png' },
    { name: '술&유흥', icon: '/assets/media/category/alcohol.png' },
    { name: '기타', icon: '/assets/media/category/alcohol.png' }
];

// 이미지 목록
const images = ref([
    '/assets/media/food/samgeob1.jpg',
    '/assets/media/food/samgeob2.jpg',
    '/assets/media/food/samgeob3.jpg',
])

</script>

<style scoped>
.carousel-image {
    width: 100%;
    /* 이미지가 Carousel의 너비에 맞춰짐 */
    height: 500px;
    /* contain : 사진 크기에 맞게, cover : carousel 에 맞게(이미지 잘림) */
    object-fit: contain;

}
</style>