<template>
  <v-app>
    <!-- App Bar / Navigation -->
    <v-app-bar app color="white" elevation="1">
      <div class="d-flex align-center">
        <v-img
          alt="Chrono Logo"
          class="shrink mr-2"
          contain
          src="https://via.placeholder.com/40x40?text=CW"
          transition="scale-transition"
          width="40"
        />
        <h1 class="text-h5 font-weight-bold primary--text">ChronoWatches</h1>
      </div>

      <v-spacer></v-spacer>

      <!-- Desktop Navigation -->
      <div class="hidden-sm-and-down">
        <v-btn text class="text-capitalize mx-1" @click="scrollToSection('hero')">Giới thiệu</v-btn>
        <v-btn text class="text-capitalize mx-1" @click="scrollToSection('collection')">Bộ sưu tập</v-btn>
        <v-btn text class="text-capitalize mx-1" @click="scrollToSection('features')">Ưu điểm</v-btn>
        <v-btn text class="text-capitalize mx-1" @click="scrollToSection('testimonials')">Phản hồi</v-btn>
        <v-btn text class="text-capitalize mx-1" @click="scrollToSection('contact')">Liên hệ</v-btn>
      </div>

      <!-- Mobile Navigation -->
      <v-app-bar-nav-icon class="hidden-md-and-up" @click="drawer = true"></v-app-bar-nav-icon>
      
      <v-btn color="primary" class="ml-4" depressed>
        <span>Shop Now</span>
      </v-btn>
    </v-app-bar>

    <!-- Mobile Navigation Drawer -->
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
      <!-- Hero Section -->
      <section id="hero" class="hero-section">
        <v-container class="py-12">
          <v-row align="center">
            <v-col cols="12" md="6" class="pr-md-10">
              <h1 class="text-h2 font-weight-bold mb-4">Timeless Elegance on Your Wrist</h1>
              <p class="text-subtitle-1 mb-6">
                Discover our collection of premium watches crafted with precision and designed for those who appreciate the art of timekeeping.
              </p>
              <div class="d-flex flex-wrap">
                <v-btn x-large color="primary" class="mr-4 mb-2" depressed @click="scrollToSection('collection')">
                  Explore Collection
                </v-btn>
                <v-btn x-large outlined class="mb-2">
                  Watch Video
                  <v-icon right>mdi-play-circle-outline</v-icon>
                </v-btn>
              </div>
              <div class="mt-8 d-flex align-center">
                <div class="mr-6">
                  <div class="text-h4 font-weight-bold">5K+</div>
                  <div class="text-subtitle-2">Happy Customers</div>
                </div>
                <div class="mr-6">
                  <div class="text-h4 font-weight-bold">150+</div>
                  <div class="text-subtitle-2">Watch Models</div>
                </div>
                <div>
                  <div class="text-h4 font-weight-bold">15+</div>
                  <div class="text-subtitle-2">Years of Excellence</div>
                </div>
              </div>
            </v-col>
            <v-col cols="12" md="6" class="text-center">
              <v-img
                src="https://images.unsplash.com/photo-1523170335258-f5ed11844a49?ixlib=rb-1.2.1&auto=format&fit=crop&w=800&q=80"
                max-width="500"
                class="mx-auto rounded-lg elevation-10"
              ></v-img>
            </v-col>
          </v-row>
        </v-container>
      </section>

      <!-- Brands Section -->
      <section class="brands-section grey lighten-4 py-6">
        <v-container>
          <div class="text-center mb-6">
            <p class="text-subtitle-1 text-uppercase font-weight-medium">Trusted by the world's best brands</p>
          </div>
          <v-row justify="center" align="center">
            <v-col cols="4" sm="2" class="text-center">
              <v-img
                src="https://via.placeholder.com/120x40?text=Brand+1"
                max-width="120"
                class="mx-auto"
              ></v-img>
            </v-col>
            <v-col cols="4" sm="2" class="text-center">
              <v-img
                src="https://via.placeholder.com/120x40?text=Brand+2"
                max-width="120"
                class="mx-auto"
              ></v-img>
            </v-col>
            <v-col cols="4" sm="2" class="text-center">
              <v-img
                src="https://via.placeholder.com/120x40?text=Brand+3"
                max-width="120"
                class="mx-auto"
              ></v-img>
            </v-col>
            <v-col cols="4" sm="2" class="text-center">
              <v-img
                src="https://via.placeholder.com/120x40?text=Brand+4"
                max-width="120"
                class="mx-auto"
              ></v-img>
            </v-col>
            <v-col cols="4" sm="2" class="text-center">
              <v-img
                src="https://via.placeholder.com/120x40?text=Brand+5"
                max-width="120"
                class="mx-auto"
              ></v-img>
            </v-col>
          </v-row>
        </v-container>
      </section>

      <!-- Featured Products Section -->
      <section id="collection" class="featured-products py-12">
        <v-container>
          <div class="text-center mb-10">
            <h2 class="text-h3 font-weight-bold mb-2">Featured Collection</h2>
            <p class="text-subtitle-1 mx-auto" style="max-width: 600px">
              Explore our handpicked selection of premium timepieces, each crafted with precision and designed for elegance.
            </p>
          </div>
          
          <v-row>
            <v-col cols="12" sm="6" md="4" v-for="(product, index) in featuredProducts" :key="index">
              <v-card class="mx-auto" max-width="400" elevation="3"  flat>
                <v-img
                  :src="product.image"
                  height="300"
                  class="grey lighten-2"
                ></v-img>
                <v-card-title>{{ product.name }}</v-card-title>
                <v-card-subtitle>{{ product.category }}</v-card-subtitle>
                <v-card-text>
                  <div class="d-flex justify-space-between align-center">
                    <div class="text-h5 primary--text font-weight-bold">${{ product.price }}</div>
                    <div>
                      <v-rating
                        :value="product.rating"
                        color="amber"
                        dense
                        half-increments
                        readonly
                        size="18"
                      ></v-rating>
                    </div>
                  </div>
                </v-card-text>
                <v-divider class="mx-4"></v-divider>
                <v-card-actions>
                  <v-btn color="primary" text>
                    View Details
                  </v-btn>
                  <v-spacer></v-spacer>
                  <v-btn color="primary" depressed>
                    Add to Cart
                  </v-btn>
                </v-card-actions>
              </v-card>
            </v-col>
          </v-row>
          
          <div class="text-center mt-8">
            <v-btn color="primary" x-large outlined>
              View All Collection
              <v-icon right>mdi-arrow-right</v-icon>
            </v-btn>
          </div>
        </v-container>
      </section>

      <!-- Features Section -->
      <section id="features" class="features-section grey lighten-4 py-12">
        <v-container>
          <div class="text-center mb-10">
            <h2 class="text-h3 font-weight-bold mb-2">Why Choose Us</h2>
            <p class="text-subtitle-1 mx-auto" style="max-width: 600px">
              We pride ourselves on quality, craftsmanship, and exceptional customer service.
            </p>
          </div>
          
          <v-row>
            <v-col cols="12" md="4" v-for="(feature, index) in features" :key="index">
              <v-card class="pa-4 h-100" flat>
                <div class="d-flex justify-center mb-4">
                  <v-avatar color="primary" size="64" class="elevation-2">
                    <v-icon dark size="32">{{ feature.icon }}</v-icon>
                  </v-avatar>
                </div>
                <h3 class="text-h5 font-weight-bold text-center mb-3">{{ feature.title }}</h3>
                <p class="text-body-1 text-center">{{ feature.description }}</p>
              </v-card>
            </v-col>
          </v-row>
        </v-container>
      </section>

      <!-- Testimonials Section -->
      <section id="testimonials" class="testimonials-section py-12">
        <v-container>
          <div class="text-center mb-10">
            <h2 class="text-h3 font-weight-bold mb-2">What Our Customers Say</h2>
            <p class="text-subtitle-1 mx-auto" style="max-width: 600px">
              Don't just take our word for it. Here's what our customers have to say about their experience.
            </p>
          </div>
          
          <v-carousel
            cycle
            hide-delimiter-background
            show-arrows-on-hover
            height="auto"
            :show-arrows="false"
          >
            <v-carousel-item v-for="(testimonial, index) in testimonials" :key="index">
              <v-sheet class="mx-auto" max-width="800">
                <v-card class="pa-8 text-center" flat>
                  <v-avatar size="100" class="mb-4">
                    <v-img :src="testimonial.avatar"></v-img>
                  </v-avatar>
                  <div class="mb-4">
                    <v-rating
                      :value="5"
                      color="amber"
                      dense
                      half-increments
                      readonly
                      size="24"
                    ></v-rating>
                  </div>
                  <p class="text-h6 font-italic mb-4">
                    "{{ testimonial.quote }}"
                  </p>
                  <h4 class="text-subtitle-1 font-weight-bold mb-1">{{ testimonial.name }}</h4>
                  <p class="text-subtitle-2 grey--text">{{ testimonial.title }}</p>
                </v-card>
              </v-sheet>
            </v-carousel-item>
          </v-carousel>
        </v-container>
      </section>

      <!-- Newsletter Section -->
      <section class="newsletter-section primary py-12">
        <v-container>
          <v-row align="center" justify="center">
            <v-col cols="12" md="6" class="text-center text-md-left">
              <h2 class="text-h4 font-weight-bold white--text mb-2">Subscribe to Our Newsletter</h2>
              <p class="text-subtitle-1 white--text mb-0">
                Stay updated with our latest collections, exclusive offers, and horological insights.
              </p>
            </v-col>
            <v-col cols="12" md="6">
              <v-form @submit.prevent="subscribeNewsletter">
                <v-row>
                  <v-col cols="12" sm="8">
                    <v-text-field
                      v-model="email"
                      label="Your Email Address"
                      outlined
                      dense
                      background-color="white"
                      hide-details
                    ></v-text-field>
                  </v-col>
                  <v-col cols="12" sm="4">
                    <v-btn
                      color="secondary"
                      depressed
                      block
                      height="40"
                      @click="subscribeNewsletter"
                    >
                      Subscribe
                    </v-btn>
                  </v-col>
                </v-row>
              </v-form>
            </v-col>
          </v-row>
        </v-container>
      </section>

      <!-- Footer / Contact Section -->
      <section id="contact" class="footer-section">
        <v-footer dark padless>
          <v-container class="py-10">
            <v-row>
              <v-col cols="12" md="4" class="mb-6 mb-md-0">
                <div class="d-flex align-center mb-4">
                  <v-img
                    alt="Chrono Logo"
                    class="shrink mr-2"
                    contain
                    src="https://via.placeholder.com/40x40?text=CW"
                    transition="scale-transition"
                    width="40"
                  />
                  <h1 class="text-h5 font-weight-bold white--text">ChronoWatches</h1>
                </div>
                <p class="text-body-2 grey--text text--lighten-1 mb-4">
                  Crafting timeless elegance since 2008. Our mission is to provide exceptional timepieces that combine traditional craftsmanship with modern innovation.
                </p>
                <div class="d-flex">
                  <v-btn icon class="mr-2">
                    <v-icon>mdi-facebook</v-icon>
                  </v-btn>
                  <v-btn icon class="mr-2">
                    <v-icon>mdi-twitter</v-icon>
                  </v-btn>
                  <v-btn icon class="mr-2">
                    <v-icon>mdi-instagram</v-icon>
                  </v-btn>
                  <v-btn icon>
                    <v-icon>mdi-pinterest</v-icon>
                  </v-btn>
                </div>
              </v-col>
              
              <v-col cols="6" sm="3" md="2">
                <h3 class="text-subtitle-1 font-weight-bold mb-4">Shop</h3>
                <v-list dense dark class="pa-0" nav>
                  <v-list-item v-for="(link, i) in shopLinks" :key="i" class="px-0">
                    <v-list-item-content>
                      <v-list-item-title class="grey--text text--lighten-1">{{ link }}</v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                </v-list>
              </v-col>
              
              <v-col cols="6" sm="3" md="2">
                <h3 class="text-subtitle-1 font-weight-bold mb-4">Company</h3>
                <v-list dense dark class="pa-0" nav>
                  <v-list-item v-for="(link, i) in companyLinks" :key="i" class="px-0">
                    <v-list-item-content>
                      <v-list-item-title class="grey--text text--lighten-1">{{ link }}</v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                </v-list>
              </v-col>
              
              <v-col cols="12" sm="6" md="4">
                <h3 class="text-subtitle-1 font-weight-bold mb-4">Contact Us</h3>
                <v-list dense dark class="pa-0">
                  <v-list-item class="px-0">
                    <v-list-item-icon class="mr-3">
                      <v-icon small>mdi-map-marker</v-icon>
                    </v-list-item-icon>
                    <v-list-item-content>
                      <v-list-item-title class="grey--text text--lighten-1">123 Luxury Lane, Watchville, WA 98765</v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                  
                  <v-list-item class="px-0">
                    <v-list-item-icon class="mr-3">
                      <v-icon small>mdi-phone</v-icon>
                    </v-list-item-icon>
                    <v-list-item-content>
                      <v-list-item-title class="grey--text text--lighten-1">+1 (555) 123-4567</v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                  
                  <v-list-item class="px-0">
                    <v-list-item-icon class="mr-3">
                      <v-icon small>mdi-email</v-icon>
                    </v-list-item-icon>
                    <v-list-item-content>
                      <v-list-item-title class="grey--text text--lighten-1">info@chronowatches.com</v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                  
                  <v-list-item class="px-0">
                    <v-list-item-icon class="mr-3">
                      <v-icon small>mdi-clock-outline</v-icon>
                    </v-list-item-icon>
                    <v-list-item-content>
                      <v-list-item-title class="grey--text text--lighten-1">Mon - Fri: 9AM - 6PM</v-list-item-title>
                    </v-list-item-content>
                  </v-list-item>
                </v-list>
              </v-col>
            </v-row>
          </v-container>
          
          <v-divider></v-divider>
          
          <v-container>
            <div class="py-4 text-center text-md-left d-flex flex-column flex-md-row justify-space-between align-center">
              <div class="grey--text text--lighten-1 text-body-2">
                &copy; {{ new Date().getFullYear() }} ChronoWatches. All rights reserved.
              </div>
              <div class="d-flex mt-4 mt-md-0">
                <a href="#" class="text-body-2 grey--text text--lighten-1 mr-4">Privacy Policy</a>
                <a href="#" class="text-body-2 grey--text text--lighten-1 mr-4">Terms of Service</a>
                <a href="#" class="text-body-2 grey--text text--lighten-1">Shipping Policy</a>
              </div>
            </div>
          </v-container>
        </v-footer>
      </section>
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: 'App',
  
  data: () => ({
    drawer: false,
    email: '',
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
        rating: 4.5,
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
    features: [
      {
        icon: 'mdi-certificate',
        title: 'Authentic Guarantee',
        description: 'Every watch comes with a certificate of authenticity and a 3-year international warranty.'
      },
      {
        icon: 'mdi-truck-delivery',
        title: 'Free Global Shipping',
        description: 'Enjoy free express shipping on all orders over $500, with delivery tracking provided.'
      },
      {
        icon: 'mdi-refresh',
        title: '30-Day Returns',
        description: 'Not completely satisfied? Return your purchase within 30 days for a full refund.'
      }
    ],
    testimonials: [
      {
        name: 'James Wilson',
        title: 'Business Executive',
        avatar: 'https://randomuser.me/api/portraits/men/32.jpg',
        quote: "The craftsmanship of my ChronoWatches timepiece is exceptional. I receive compliments every time I wear it to meetings. It's not just a watch, it's a statement piece that reflects my personal style."
      },
      {
        name: 'Sophia Chen',
        title: 'Architect',
        avatar: 'https://randomuser.me/api/portraits/women/44.jpg',
        quote: "As someone who appreciates design, I'm impressed by the attention to detail in my watch. The customer service was outstanding, and the packaging made the unboxing experience special."
      },
      {
        name: 'Robert Johnson',
        title: 'Watch Collector',
        avatar: 'https://randomuser.me/api/portraits/men/46.jpg',
        quote: "I've been collecting watches for over 15 years, and ChronoWatches offers exceptional value for the quality. Their limited edition pieces are particularly impressive and hold their value well."
      }
    ],
    shopLinks: ['Men\'s Watches', 'Women\'s Watches', 'Luxury Collection', 'Sport Watches', 'Accessories'],
    companyLinks: ['About Us', 'Our Story', 'Careers', 'Press', 'Blog']
  }),

  methods: {
    scrollToSection(sectionId) {
      const element = document.getElementById(sectionId);
      if (element) {
        // Get the top position of the element relative to the viewport
        const offsetTop = element.getBoundingClientRect().top + window.pageYOffset;
        
        // Account for fixed header height
        const headerOffset = 64; // Adjust this value based on your header height
        const offsetPosition = offsetTop - headerOffset;
        
        // Smooth scroll to the element
        window.scrollTo({
          top: offsetPosition,
          behavior: 'smooth'
        });
      }
    },
    
    subscribeNewsletter() {
      if (this.email) {
        alert(`Thank you for subscribing with: ${this.email}`);
        this.email = '';
      }
    }
  }
};
</script>

<style>
.hero-section {
  background: linear-gradient(to right, rgba(255,255,255,0.95), rgba(255,255,255,0.8)), 
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