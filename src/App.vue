<template>

  <v-app>
    <div>
      <v-app-bar app>
        <v-toolbar-title>
          <span class="text-h5 font-weight-bold primary--text">TuitenthaiWatches</span>
        </v-toolbar-title>
        <v-spacer></v-spacer>
        <div class="hidden-sm-and-down">
          <v-btn depressed text class="mx-1" v-for="(item, index) in itemsnavbar" :key="index">
            {{ item }}
          </v-btn>
          <v-btn color="primary" class="ml-4">Mua ngay</v-btn>
        </div>
        <v-app-bar-nav-icon class="hidden-md-and-up" @click="drawer = true"></v-app-bar-nav-icon>
      </v-app-bar>
      <v-navigation-drawer v-model="drawer" absolute temporary right>
        <v-list nav dense>
          <v-list-item-group>
            <v-list-item @click="scrollToSection('hero'); drawer = false">
              <v-list-item-title>Home</v-list-item-title>
            </v-list-item>
            <v-list-item @click="scrollToSection('collection'); drawer = false">
              <v-list-item-title>Collection</v-list-item-title>
            </v-list-item>
            <v-list-item @click="scrollToSection('features'); drawer = false">
              <v-list-item-title>Features</v-list-item-title>
            </v-list-item>
            <v-list-item @click="scrollToSection('testimonials'); drawer = false">
              <v-list-item-title>Reviews</v-list-item-title>
            </v-list-item>
            <v-list-item @click="scrollToSection('contact'); drawer = false">
              <v-list-item-title>Contact</v-list-item-title>
            </v-list-item>
          </v-list-item-group>
        </v-list>
      </v-navigation-drawer>

      <v-main>
        <v-container class="">
          <section id="hero" class="hero-section">
            <v-container class="py-12">
              <v-row align="center">
                <v-col cols="12" md="6" class="pr-md-10">
                  <h1 class="text-h3 font-weight-bold mb-4">Vẻ Đẹp Tinh Tế Đồng Hành Cùng Thời Gian</h1>
                  <p class="text-subtitle-1 mb-6">
                    Khám phá bộ sưu tập đồng hồ cao cấp được chế tác tỉ mỉ và dành cho những người yêu thích nghệ
                    thuật từ thời gian.
                  </p>
                  <div class="d-flex flex-wrap">
                    <v-btn x-large color="primary" class="mr-4 mb-2" depressed @click="scrollToSection('collection')">
                      Khám phá bộ sưu tập
                    </v-btn>
                    <v-btn x-large outlined class="mb-2">
                      Watch Video
                      <v-icon right>mdi-play-circle-outline</v-icon>
                    </v-btn>
                  </div>
                  <div class="mt-8 d-flex align-center">
                    <div class="mr-6 align-center">
                      <div class="text-h4 font-weight-bold">5K+</div>
                      <div class="text-subtitle-2">Khách Hàng Hài Lòng</div>
                    </div>
                    <div class="mr-6 align-center">
                      <div class="text-h4 font-weight-bold">150+</div>
                      <div class="text-subtitle-2">Mẫu Đồng Hồ</div>
                    </div>
                    <div class="align-center">
                      <div class="text-h4 font-weight-bold">15+</div>
                      <div class="text-subtitle-2">Năm kinh nghiệm</div>
                    </div>
                  </div>
                </v-col>
                <v-col cols="12" md="6" class="text-center">
                  <v-img
                    src="https://images.unsplash.com/photo-1523170335258-f5ed11844a49?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80"
                    max-width="500" class="mx-auto rounded-lg elevation-10"></v-img>
                </v-col>
              </v-row>
            </v-container>
          </section>
        </v-container>

        <section class="brands-section grey lighten-4 py-6">
          <v-container>
            <div class="text-center mb-6">
              <p class="text-subtitle-1 text-uppercase font-weight-medium">Được Các Thương Hiệu Hàng Đầu Tin Dùng</p>
            </div>
            <v-row justify="center" align="center">
              <v-col v-for="(item, index) in itemsbrand" :key="index" cols="4" sm="2" class="text-center">
                <v-img :src=item max-width="120" class="mx-auto"></v-img>
              </v-col>
            </v-row>
          </v-container>
        </section>
        <v-container  class="featured-products py-12">
          <v-col align="center">
            <div class="text-h4 text-uppercase font-weight-medium">Dấu Ấn Cá Nhân</div>
            <div class="mx-auto text-subtitle-1 mb-10" style="max-width: 600px;">Tôn vinh phong cách của bạn với bộ sưu tập
              đồng hồ cao cấp đồng hành cùng bạn trên mọi khoảnh khắc.</div>
            <div class="mb-10">
              <v-row>
                <v-col cols="12" sm="6" md="4" v-for="(item, index) in featuredProducts" :key="index">
                  <v-card class="mx-auto" max-width="400" elevation="3" flat>
                    <v-img class="grey lighten-2" height="250" :src=item?.image></v-img>
                    <v-card-title>{{ item?.name }}</v-card-title>
                    <v-card-subtitle class="text-left">{{ item?.category }}</v-card-subtitle>
                    <v-card-text>
                      <div class="d-flex justify-space-between align-center">
                        <div class="text-h5 primary--text font-weight-bold">
                          ${{ item?.price }}
                        </div>
                        <div>
                          <v-rating :value="item.rating" color="amber" dense half-increments readonly
                            size="18"></v-rating>
                        </div>
                      </div>
                      <v-divider></v-divider>
                      <v-card-actions class="d-flex justify-space-between align-center">
                        <v-btn text>Chi tiết</v-btn>
                        <v-btn color="primary">Mua ngay </v-btn>
                      </v-card-actions>
                    </v-card-text>
                  </v-card>
                </v-col>
              </v-row>
            </div>
            <div>
              <v-btn color="primary" outlined> <v-icon>mdi-arrow-right</v-icon>Xem thêm</v-btn>
            </div>
          </v-col>
        </v-container>
        <section>
        </section>
      </v-main>
    </div>
  </v-app>
</template>

<script>
export default {
  data() {
    return {
      itemsnavbar: ["Giới thiệu", "Tuyển tập", "Ưu điểm", "Phản hồi", "Liên hệ"],
      itemsbrand: [
        "https://upload.wikimedia.org/wikipedia/commons/f/f4/Logo_da_Rolex.png",
        "https://upload.wikimedia.org/wikipedia/commons/thumb/f/fb/Omega_Logo.svg/640px-Omega_Logo.svg.png",
        "https://upload.wikimedia.org/wikipedia/commons/thumb/2/2c/Seiko_logo.svg/640px-Seiko_logo.svg.png",
        "https://upload.wikimedia.org/wikipedia/commons/5/51/Citizen_logo.svg"
      ],
      featuredProducts: [
        {
          name: 'Classic Chronograph',
          category: 'Luxury Collection',
          price: '1,299',
          rating: 4.8,
          image: 'https://images.unsplash.com/photo-1522312346375-d1a52e2b99b3?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80'
        },
        {
          name: 'Diver Pro 200M',
          category: 'Sport Collection',
          price: '899',
          rating: 4.1,
          image: 'https://images.unsplash.com/photo-1508685096489-7aacd43bd3b1?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80'
        },
        {
          name: 'Minimalist Series',
          category: 'Casual Collection',
          price: '599',
          rating: 4.7,
          image: 'https://images.unsplash.com/photo-1539874754764-5a96559165b0?ixlib=rb-1.2.1&auto=format&fit=crop&w=600&q=80'
        }
      ],
      drawer: false,
      show: false,
    }
  }
}
</script>

<style scoped>
.hero-section {
  background: linear-gradient(to right, rgba(255, 255, 255, 0.95), rgba(255, 255, 255, 0.8)),
    url('https://images.unsplash.com/photo-1619946794135-5bc917a27793?ixlib=rb-1.2.1&auto=format&fit=crop&w=1500&q=80') no-repeat center center;
  background-size: cover;
}

.v-application {
  font-family: 'Poppins', sans-serif !important;
  scroll-behavior: smooth;
}

html {
  scroll-behavior: smooth;
}

.v-card {
  transition: transform 0.3s ease;
}

.v-card:hover {
  transform: translateY(-5px);
}

.v-btn--active {
  color: var(--v-primary-base) !important;
  font-weight: bold;
}
</style>
