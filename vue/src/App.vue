<template>
  <v-app>
    <v-app-bar app color="blue" dark fixed>
      <v-app-bar-nav-icon @click="menuOpen = !menuOpen">
        <v-menu v-model="menuOpen" offset-y>
          <template v-slot:activator="{ on, attrs }">
            <v-btn icon v-bind="attrs" v-on="on">
              <v-icon>mdi-menu</v-icon>
            </v-btn>
          </template>
          <v-list>
            <v-list-item @click="handleMenuItemClick('메뉴 - 1')">
              <v-list-item-title style="w200">메뉴 - 1</v-list-item-title>
            </v-list-item>
            <v-list-item @click="handleMenuItemClick('메뉴 - 2')">
              <v-list-item-title>메뉴 - 2</v-list-item-title>
            </v-list-item>
          </v-list>
        </v-menu>
      </v-app-bar-nav-icon>
      <v-toolbar-title>201968039 김세현 기말과제</v-toolbar-title>
      <v-spacer></v-spacer>
      <naver></naver>
      <!-- 더 보기 버튼 -->
      <v-btn icon @click="showPopup = true">
        <v-icon>more_vert</v-icon>
      </v-btn>
    </v-app-bar>
    <v-main>
      <Discount></Discount>
			<v-row>
				<SideBanner></SideBanner>
				<v-container>
						<v-row>
							<v-col cols="12" sm="6" md="3" lg="3" xl="2" v-for="item in aPictures" :key="item.key">
								<v-card height="330px">
									<v-img :src="item.url" height="200px"></v-img>
									<v-card-title>
										<h1 class="title grey--text text--darken-3 mb-3">{{ item.title }}</h1>
										<p class="body-2 grey--text">{{ item.info }}</p>
									</v-card-title>
								</v-card>
							</v-col>
						</v-row>
				</v-container>
			</v-row>
    </v-main>
    <v-footer fixed>
      <div class="mx-auto">&copy; 201968039 김세현</div>
    </v-footer>
    <!-- 팝업 창 -->
    <v-dialog v-model="showPopup" max-width="400">
      <v-card>
        <v-card-text class="text-center" style="padding-top: 24px">아무 것도 없는 버튼입니다.</v-card-text>
        <v-card-actions>
          <v-btn text @click="showPopup = false">닫기</v-btn>
        </v-card-actions>
      </v-card>
    </v-dialog>
  </v-app>
</template>

<script>
import Discount from '@/components/Discount.vue';
import oPictureData from '@/datasources/picture-data';
import naver from '@/components/naver.vue';
import SideBanner from '@/components/SideBanner.vue';
import menu from '@/components/menu.vue';

export default {
  data() {
    return {
      aPictures: oPictureData.aPictures,
      showPopup: false, // 팝업 창 표시 여부를 관리하는 데이터
    };
  },
  name: 'App',
  components: {
		SideBanner,
    naver,
    Discount,
    menu,
  },
};
</script>

