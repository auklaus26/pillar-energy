<template>
  <el-config-provider>
    <el-container class="app-shell">
      <!-- Top Nav -->
      <el-header class="app-header">
        <div class="brand" @click="scrollTo('home')">
          <div class="brand-mark">P</div>
          <div class="brand-text">
            <div class="brand-name">PILLAR ENERGY</div>
            <div class="brand-sub">Built on pillars. Built to last.</div>
          </div>
        </div>

        <el-menu
          mode="horizontal"
          :default-active="active"
          class="top-menu"
          :ellipsis="false"
          @select="onSelect"
        >
          <el-menu-item index="home">Home</el-menu-item>
          <el-menu-item index="about">About Us</el-menu-item>
          <el-menu-item index="services">Services</el-menu-item>
          <el-menu-item index="projects">Projects</el-menu-item>
          <el-menu-item index="contact">Contact</el-menu-item>
          <!-- <el-menu-item index="zh">中文</el-menu-item> -->
        </el-menu>

        <div class="header-actions">
          <el-tooltip content="Default: English" placement="bottom">
            <el-switch
              v-model="isZh"
              active-text="中文"
              inactive-text="EN"
              inline-prompt
              @change="onLangToggle"
            />
          </el-tooltip>

          <el-button type="primary" class="cta" @click="scrollTo('contact')">
            Contact Us
          </el-button>
        </div>
      </el-header>

      <el-main class="app-main">
        <!-- HOME -->
        <section :id="ids.home" class="section hero">
          <div class="hero-bg" aria-hidden="true"></div>

          <el-row :gutter="20" align="middle" class="hero-row">
            <el-col :xs="24" :md="14">
              <div class="hero-kicker">{{ t.home.kicker }}</div>
              <h1 class="hero-title">
                <span class="hero-title-brand">PILLAR ENERGY</span>
                <span class="hero-title-line">{{ t.home.tagline }}</span>
              </h1>
              <p class="hero-desc">{{ t.home.desc }}</p>

              <div class="hero-actions">
                <el-button type="primary" size="large" @click="scrollTo('services')">
                  Our Services
                </el-button>
                <el-button size="large" @click="scrollTo('contact')">Contact Us</el-button>
              </div>

              <div class="hero-note">
                <span class="dot"></span>
                <span>{{ t.home.note }}</span>
              </div>
            </el-col>

            <el-col :xs="24" :md="10">
              <el-card class="hero-card" shadow="hover">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.home.whatWeDoTitle }}</span>
                    <el-tag type="success" effect="light">Australia</el-tag>
                  </div>
                </template>

                <p class="muted">{{ t.home.whatWeDoLead }}</p>

                <el-row :gutter="12" class="pill-grid">
                  <el-col :xs="12" :sm="12">
                    <el-card class="pill" shadow="never">
                      <div class="pill-title">{{ t.home.pills[0].title }}</div>
                      <div class="pill-desc">{{ t.home.pills[0].desc }}</div>
                    </el-card>
                  </el-col>
                  <el-col :xs="12" :sm="12">
                    <el-card class="pill" shadow="never">
                      <div class="pill-title">{{ t.home.pills[1].title }}</div>
                      <div class="pill-desc">{{ t.home.pills[1].desc }}</div>
                    </el-card>
                  </el-col>
                  <el-col :xs="12" :sm="12">
                    <el-card class="pill" shadow="never">
                      <div class="pill-title">{{ t.home.pills[2].title }}</div>
                      <div class="pill-desc">{{ t.home.pills[2].desc }}</div>
                    </el-card>
                  </el-col>
                  <el-col :xs="12" :sm="12">
                    <el-card class="pill" shadow="never">
                      <div class="pill-title">{{ t.home.pills[3].title }}</div>
                      <div class="pill-desc">{{ t.home.pills[3].desc }}</div>
                    </el-card>
                  </el-col>
                </el-row>
              </el-card>
            </el-col>
          </el-row>
        </section>

        <!-- ABOUT -->
        <section :id="ids.about" class="section">
          <div class="section-head">
            <h2 class="section-title">{{ t.about.title }}</h2>
            <p class="section-sub">{{ t.about.sub }}</p>
          </div>

          <el-row :gutter="16">
            <el-col :xs="24" :md="12">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.about.whoTitle }}</span>
                  </div>
                </template>
                <p class="p">{{ t.about.whoP1 }}</p>
                <p class="p muted">{{ t.about.whoP2 }}</p>
              </el-card>
            </el-col>

            <el-col :xs="24" :md="12">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.about.whyTitle }}</span>
                  </div>
                </template>
                <p class="p">{{ t.about.whyP1 }}</p>
                <p class="p muted">{{ t.about.whyP2 }}</p>
              </el-card>
            </el-col>
          </el-row>

          <el-row :gutter="16" style="margin-top: 16px">
            <el-col :xs="24" :md="16">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.about.approachTitle }}</span>
                  </div>
                </template>

                <el-row :gutter="12">
                  <el-col :xs="24" :sm="8">
                    <el-card class="mini" shadow="never">
                      <div class="mini-title">{{ t.about.approach[0].title }}</div>
                      <div class="mini-desc">{{ t.about.approach[0].desc }}</div>
                    </el-card>
                  </el-col>
                  <el-col :xs="24" :sm="8">
                    <el-card class="mini" shadow="never">
                      <div class="mini-title">{{ t.about.approach[1].title }}</div>
                      <div class="mini-desc">{{ t.about.approach[1].desc }}</div>
                    </el-card>
                  </el-col>
                  <el-col :xs="24" :sm="8">
                    <el-card class="mini" shadow="never">
                      <div class="mini-title">{{ t.about.approach[2].title }}</div>
                      <div class="mini-desc">{{ t.about.approach[2].desc }}</div>
                    </el-card>
                  </el-col>
                </el-row>
              </el-card>
            </el-col>

            <el-col :xs="24" :md="8">
              <el-card shadow="hover" class="card vision">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.about.visionTitle }}</span>
                    <el-tag type="info" effect="light">Long-term</el-tag>
                  </div>
                </template>
                <p class="p">{{ t.about.visionP }}</p>
              </el-card>
            </el-col>
          </el-row>
        </section>

        <!-- SERVICES -->
        <section :id="ids.services" class="section">
          <div class="section-head">
            <h2 class="section-title">{{ t.services.title }}</h2>
            <p class="section-sub">{{ t.services.sub }}</p>
          </div>

          <el-row :gutter="16">
            <el-col :xs="24" :md="12">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.services.items[0].title }}</span>
                    <el-tag type="success" effect="light">Solar + Battery</el-tag>
                  </div>
                </template>
                <p class="p">{{ t.services.items[0].desc }}</p>
              </el-card>
            </el-col>

            <el-col :xs="24" :md="12">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.services.items[1].title }}</span>
                    <el-tag type="primary" effect="light">Storage</el-tag>
                  </div>
                </template>
                <p class="p">{{ t.services.items[1].desc }}</p>
                <el-divider />
                <el-row :gutter="10">
                  <el-col :xs="24" :sm="12">
                    <el-tag effect="light" class="tag-block">{{ t.services.items[1].bullets[0] }}</el-tag>
                  </el-col>
                  <el-col :xs="24" :sm="12">
                    <el-tag effect="light" class="tag-block">{{ t.services.items[1].bullets[1] }}</el-tag>
                  </el-col>
                  <el-col :xs="24" :sm="24" style="margin-top: 8px">
                    <el-tag effect="light" class="tag-block">{{ t.services.items[1].bullets[2] }}</el-tag>
                  </el-col>
                </el-row>
              </el-card>
            </el-col>
          </el-row>

          <el-row :gutter="16" style="margin-top: 16px">
            <el-col :xs="24" :md="12">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.services.items[2].title }}</span>
                    <el-tag type="warning" effect="light">Compliance</el-tag>
                  </div>
                </template>

                <el-row :gutter="10">
                  <el-col :xs="24" :sm="12">
                    <el-tag effect="light" class="tag-block">{{ t.services.items[2].bullets[0] }}</el-tag>
                  </el-col>
                  <el-col :xs="24" :sm="12">
                    <el-tag effect="light" class="tag-block">{{ t.services.items[2].bullets[1] }}</el-tag>
                  </el-col>
                  <el-col :xs="24" :sm="24" style="margin-top: 8px">
                    <el-tag effect="light" class="tag-block">{{ t.services.items[2].bullets[2] }}</el-tag>
                  </el-col>
                </el-row>

                <el-divider />
                <p class="p muted">{{ t.services.items[2].desc }}</p>
              </el-card>
            </el-col>

            <el-col :xs="24" :md="12">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.services.items[3].title }}</span>
                    <el-tag type="info" effect="light">Project-based</el-tag>
                  </div>
                </template>

                <p class="p">{{ t.services.items[3].desc }}</p>
                <el-divider />
                <el-row :gutter="10">
                  <el-col :xs="24">
                    <el-tag effect="light" class="tag-block">{{ t.services.items[3].bullets[0] }}</el-tag>
                  </el-col>
                  <el-col :xs="24" style="margin-top: 8px">
                    <el-tag effect="light" class="tag-block">{{ t.services.items[3].bullets[1] }}</el-tag>
                  </el-col>
                  <el-col :xs="24" style="margin-top: 8px">
                    <el-tag effect="light" class="tag-block">{{ t.services.items[3].bullets[2] }}</el-tag>
                  </el-col>
                </el-row>
              </el-card>
            </el-col>
          </el-row>
        </section>

        <!-- PROJECTS (status only) -->
        <section :id="ids.projects" class="section">
          <div class="section-head">
            <h2 class="section-title">{{ t.projects.title }}</h2>
            <p class="section-sub">{{ t.projects.sub }}</p>
          </div>

          <el-row :gutter="16">
            <el-col :xs="24" :md="12">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.projects.demoTitle }}</span>
                    <el-tag type="success" effect="light">Status view</el-tag>
                  </div>
                </template>

                <el-card shadow="never" class="project">
                  <div class="project-top">
                    <div class="project-name">{{ t.projects.demo[0].name }}</div>
                    <el-tag type="success" effect="light">{{ t.projects.demo[0].status }}</el-tag>
                  </div>
                  <div class="project-meta">
                    <div><span class="k">{{ t.projects.scale }}</span> {{ t.projects.demo[0].scale }}</div>
                    <div><span class="k">{{ t.projects.type }}</span> {{ t.projects.demo[0].type }}</div>
                  </div>
                </el-card>
              </el-card>
            </el-col>

            <el-col :xs="24" :md="12">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.projects.planTitle }}</span>
                    <el-tag type="warning" effect="light">Planning</el-tag>
                  </div>
                </template>

                <el-card v-for="(p, i) in t.projects.planning" :key="i" shadow="never" class="project">
                  <div class="project-top">
                    <div class="project-name">{{ p.name }}</div>
                    <el-tag type="warning" effect="light">{{ p.status }}</el-tag>
                  </div>
                  <div class="project-meta">
                    <div><span class="k">{{ t.projects.type }}</span> {{ p.type }}</div>
                  </div>
                </el-card>

                <el-alert
                  style="margin-top: 12px"
                  type="info"
                  :closable="false"
                  show-icon
                  :title="t.projects.privacy"
                />
              </el-card>
            </el-col>
          </el-row>
        </section>

        <!-- CONTACT -->
        <section :id="ids.contact" class="section contact">
          <div class="section-head">
            <h2 class="section-title">{{ t.contact.title }}</h2>
            <p class="section-sub">{{ t.contact.sub }}</p>
          </div>

          <el-row :gutter="16">
            <el-col :xs="24" :md="10">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.contact.infoTitle }}</span>
                  </div>
                </template>

                <div class="info-list">
                  <div class="info-item">
                    <div class="info-k">{{ t.contact.emailLabel }}</div>
                    <div class="info-v">
                      <el-link type="primary" href="mailto:info@pillarenergy.com.au" :underline="false">
                        info@pillarenergy.com.au
                      </el-link>
                    </div>
                  </div>
                  <div class="info-item">
                    <div class="info-k">{{ t.contact.phoneLabel }}</div>
                    <div class="info-v">{{ t.contact.phoneValue }}</div>
                  </div>
                  <div class="info-item">
                    <div class="info-k">{{ t.contact.locationLabel }}</div>
                    <div class="info-v">{{ t.contact.locationValue }}</div>
                  </div>
                </div>

                <el-divider />
                <el-alert type="success" :closable="false" show-icon :title="t.contact.note" />
              </el-card>
            </el-col>

            <el-col :xs="24" :md="14">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>{{ t.contact.formTitle }}</span>
                    <el-tag type="info" effect="light">Zendesk / Email</el-tag>
                  </div>
                </template>

                <el-form
                  ref="formRef"
                  :model="form"
                  :rules="rules"
                  label-position="top"
                  class="contact-form"
                >
                  <el-row :gutter="12">
                    <el-col :xs="24" :sm="12">
                      <el-form-item :label="t.contact.fields.name" prop="name">
                        <el-input v-model="form.name" :placeholder="t.contact.placeholders.name" />
                      </el-form-item>
                    </el-col>
                    <el-col :xs="24" :sm="12">
                      <el-form-item :label="t.contact.fields.email" prop="email">
                        <el-input v-model="form.email" :placeholder="t.contact.placeholders.email" />
                      </el-form-item>
                    </el-col>
                  </el-row>

                  <el-row :gutter="12">
                    <el-col :xs="24" :sm="12">
                      <el-form-item :label="t.contact.fields.phone" prop="phone">
                        <el-input v-model="form.phone" :placeholder="t.contact.placeholders.phone" />
                      </el-form-item>
                    </el-col>
                    <el-col :xs="24" :sm="12">
                      <el-form-item :label="t.contact.fields.subject" prop="subject">
                        <el-input v-model="form.subject" :placeholder="t.contact.placeholders.subject" />
                      </el-form-item>
                    </el-col>
                  </el-row>

                  <el-form-item :label="t.contact.fields.message" prop="message">
                    <el-input
                      v-model="form.message"
                      type="textarea"
                      :rows="5"
                      :placeholder="t.contact.placeholders.message"
                      maxlength="1200"
                      show-word-limit
                    />
                  </el-form-item>

                  <el-alert
                    type="info"
                    show-icon
                    :closable="false"
                    class="form-hint"
                    :title="t.contact.routingHint"
                  />

                  <div class="form-actions">
                    <el-button @click="resetForm">{{ t.contact.actions.reset }}</el-button>
                    <el-button type="primary" :loading="sending" @click="submitForm">
                      {{ t.contact.actions.submit }}
                    </el-button>
                  </div>
                </el-form>
              </el-card>
            </el-col>
          </el-row>
        </section>

        <!-- 中文页面（简化版） -->
        <section :id="ids.zh" class="section">
          <div class="section-head">
            <h2 class="section-title">中文页面（简化版）</h2>
            <p class="section-sub">英文为默认语言，中文为辅助信任页面，不做完全镜像。</p>
          </div>

          <el-row :gutter="16">
            <el-col :xs="24" :md="12">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>关于我们</span>
                  </div>
                </template>
                <p class="p">
                  PILLAR ENERGY（擎能能源）是一家立足澳大利亚的新能源与储能服务品牌，由 WYNNSEAS GLOBAL PTY LTD 运营。
                </p>
                <p class="p muted">
                  我们以系统结构与合规为基础，为住宅及工商业客户提供长期可运行的能源解决方案。
                </p>
              </el-card>
            </el-col>

            <el-col :xs="24" :md="12">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>我们的理念</span>
                    <el-tag type="success" effect="light">立于根基，行至久远</el-tag>
                  </div>
                </template>
                <p class="p">
                  PILLAR 代表支柱与基础。我们以系统化思维看待能源项目，强调合规、安全与长期运行，而非一次性成交。
                </p>
                <p class="p muted">
                  从系统设计、设备选择到施工与合规，每一个环节，都是支撑长期运行的“基石”。
                </p>
              </el-card>
            </el-col>
          </el-row>

          <el-row :gutter="16" style="margin-top: 16px">
            <el-col :xs="24" :md="16">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>服务方向</span>
                  </div>
                </template>
                <el-row :gutter="10">
                  <el-col :xs="24" :sm="12">
                    <el-tag effect="light" class="tag-block">太阳能与储能系统</el-tag>
                  </el-col>
                  <el-col :xs="24" :sm="12">
                    <el-tag effect="light" class="tag-block">能源存储解决方案</el-tag>
                  </el-col>
                  <el-col :xs="24" :sm="12" style="margin-top: 8px">
                    <el-tag effect="light" class="tag-block">住宅及工商业电气安装</el-tag>
                  </el-col>
                  <el-col :xs="24" :sm="12" style="margin-top: 8px">
                    <el-tag effect="light" class="tag-block">项目型能源系统支持</el-tag>
                  </el-col>
                </el-row>
              </el-card>
            </el-col>

            <el-col :xs="24" :md="8">
              <el-card shadow="hover" class="card">
                <template #header>
                  <div class="card-header">
                    <span>联系我们</span>
                  </div>
                </template>
                <p class="p">欢迎通过官网联系表单或邮箱与我们沟通项目需求。</p>
                <p class="p muted">我们将以项目化方式进行评估与回应。</p>
                <el-button type="primary" @click="scrollTo('contact')">前往联系表单</el-button>
              </el-card>
            </el-col>
          </el-row>
        </section>
      </el-main>

      <el-footer class="app-footer">
        <div class="footer-inner">
          <div class="footer-left">
            <div class="footer-brand">PILLAR ENERGY</div>
            <div class="footer-meta">Melbourne, Australia · info@pillarenergy.com.au</div>
          </div>
          <div class="footer-right">
            <el-link :underline="false" @click="scrollTo('home')">Back to top</el-link>
          </div>
        </div>
      </el-footer>
    </el-container>
  </el-config-provider>
</template>

<script setup lang="ts">
import { computed, reactive, ref } from 'vue'
import type { FormInstance, FormRules } from 'element-plus'
import { ElMessage } from 'element-plus'

type NavKey = 'home' | 'about' | 'services' | 'projects' | 'contact' | 'zh'

const ids: Record<NavKey, string> = {
  home: 'home',
  about: 'about',
  services: 'services',
  projects: 'projects',
  contact: 'contact',
  zh: 'zh',
}

const active = ref<NavKey>('home')

/**
 * Language
 * Default EN, Chinese is auxiliary (simplified page only).
 */
const isZh = ref(false)

const copyEN = {
  home: {
    kicker: 'Australia-based energy solutions',
    tagline: 'Built on pillars. Built to last.',
    desc:
      'Structured, compliant, and long-term energy systems for residential, commercial, and project-based clients.',
    note:
      'We believe real energy solutions are not built on trends, but on solid foundations.',
    whatWeDoTitle: 'What We Do',
    whatWeDoLead:
      'We deliver energy systems designed as long-term foundations — not short-term add-ons.',
    pills: [
      { title: 'Solar & Battery', desc: 'System-first planning and delivery' },
      { title: 'Energy Storage', desc: 'Future-ready configurations' },
      { title: 'Electrical Works', desc: 'Residential & commercial installations' },
      { title: 'Project Support', desc: 'Coordination across broader projects' },
    ],
  },
  about: {
    title: 'About Us',
    sub: 'System thinking, compliance, and long-term reliability.',
    whoTitle: 'Who We Are',
    whoP1: 'PILLAR ENERGY is an energy services brand operated by WYNNSEAS GLOBAL PTY LTD.',
    whoP2:
      'We support residential and commercial clients with structured, compliant, and project-driven energy systems.',
    whyTitle: 'Why “PILLAR”',
    whyP1:
      'The name PILLAR reflects our belief that energy systems should be built as foundations, not short-term solutions.',
    whyP2:
      'We treat energy systems as structural components of a project — designed to support long-term operation, compliance, and reliability.',
    approachTitle: 'Our Approach',
    approach: [
      { title: 'System thinking', desc: 'Over individual products' },
      { title: 'Projects', desc: 'Over one-off installations' },
      { title: 'Compliance', desc: 'A baseline, not an option' },
    ],
    visionTitle: 'Our Vision',
    visionP:
      'To become a trusted pillar for long-term energy systems, supporting residential and commercial projects with stability, compliance, and system-level thinking.',
  },
  services: {
    title: 'Services',
    sub: 'From planning to delivery, every system is treated as part of a broader project.',
    items: [
      {
        title: 'Solar & Battery Systems',
        desc:
          'We support the planning and delivery of solar and battery systems for residential, commercial, and project-based applications. Systems are assessed based on suitability, integration, and long-term operational performance.',
      },
      {
        title: 'Energy Storage Solutions',
        desc:
          'Energy storage solutions designed to support evolving energy needs, planned with long-term operation and compliance in mind.',
        bullets: ['Stand-alone battery systems', 'Hybrid solar + battery systems', 'Future-ready system configurations'],
      },
      {
        title: 'Electrical Installations',
        desc:
          'All electrical works are delivered in accordance with Australian standards and project requirements.',
        bullets: ['Residential electrical installations', 'Commercial electrical installations', 'Energy-related electrical works'],
      },
      {
        title: 'Project-Based Energy Services',
        desc:
          'For clients and partners seeking a structured approach, we support energy projects as part of the project structure — not isolated components.',
        bullets: [
          'Feasibility and system planning support',
          'Technical coordination and system design alignment',
          'Partner-based delivery and implementation support',
        ],
      },
    ],
  },
  projects: {
    title: 'Projects',
    sub: 'Selected projects & demonstration cases (status display only).',
    demoTitle: 'Demonstration Projects',
    planTitle: 'Projects in Planning',
    scale: 'System Scale:',
    type: 'System Type:',
    privacy: 'Project details are presented at a system and status level to respect client privacy.',
    demo: [
      {
        name: 'Residential Battery System',
        scale: '10kW Solar + 20kWh Battery',
        type: 'Solar + Battery',
        status: 'Demonstration Project',
      },
    ],
    planning: [
      { name: 'Residential Energy System Planning', type: 'Solar + Battery', status: 'Planning' },
      { name: 'Small Commercial Energy Storage Planning', type: 'Battery Storage', status: 'Planning' },
    ],
  },
  contact: {
    title: 'Contact',
    sub: 'All enquiries are handled through our support system to ensure clear communication and proper follow-up.',
    infoTitle: 'Get in Touch',
    emailLabel: 'Email',
    phoneLabel: 'Phone',
    phoneValue: '1300 / 1800 (coming soon)',
    locationLabel: 'Location',
    locationValue: 'Melbourne, Australia',
    note: 'If you would like to discuss an energy system or project, please contact us through the form.',
    formTitle: 'Contact Form',
    routingHint:
      'Integration note: submit to Zendesk ticket API or send to your email endpoint. Configure in code where marked.',
    fields: {
      name: 'Full Name',
      email: 'Email',
      phone: 'Phone (optional)',
      subject: 'Subject',
      message: 'Message',
    },
    placeholders: {
      name: 'e.g. Alex Johnson',
      email: 'e.g. alex@email.com',
      phone: 'e.g. +61 4xx xxx xxx',
      subject: 'What can we help with?',
      message: 'Describe your project needs or questions...',
    },
    actions: {
      reset: 'Reset',
      submit: 'Submit',
    },
  },
}

const t = computed(() => copyEN)

/**
 * Contact form
 * NOTE: Replace `CONTACT_ENDPOINT` with your backend/Zendesk proxy endpoint.
 * - For security, do NOT call Zendesk API directly from browser with secrets.
 */
const formRef = ref<FormInstance>()
const form = reactive({
  name: '',
  email: '',
  phone: '',
  subject: '',
  message: '',
})

const rules: FormRules = {
  name: [{ required: true, message: 'Please enter your name.', trigger: 'blur' }],
  email: [
    { required: true, message: 'Please enter your email.', trigger: 'blur' },
    { type: 'email', message: 'Please enter a valid email.', trigger: 'blur' },
  ],
  subject: [{ required: true, message: 'Please enter a subject.', trigger: 'blur' }],
  message: [{ required: true, message: 'Please enter a message.', trigger: 'blur' }],
}

const sending = ref(false)

function onSelect(key: string) {
  active.value = key as NavKey
  scrollTo(key as NavKey)
}

function scrollTo(key: NavKey) {
  const el = document.getElementById(ids[key])
  if (!el) return
  el.scrollIntoView({ behavior: 'smooth', block: 'start' })
}

function onLangToggle() {
  // Default language is English. Chinese is an auxiliary section, not a full mirror.
  // Toggle simply navigates to Chinese section when switched on.
  if (isZh.value) {
    active.value = 'zh'
    scrollTo('zh')
  } else {
    active.value = 'home'
    scrollTo('home')
  }
}

function resetForm() {
  formRef.value?.resetFields()
}

async function submitForm() {
  if (!formRef.value) return
  await formRef.value.validate(async (valid) => {
    if (!valid) return

    sending.value = true
    try {
      // ✅ Replace this with your own endpoint (server / Zendesk proxy / email service).
      // Example: /api/contact -> server sends Zendesk ticket or email
      const CONTACT_ENDPOINT = '/api/contact'

      const resp = await fetch(CONTACT_ENDPOINT, {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
          brand: 'PILLAR ENERGY',
          ...form,
          source: 'website',
          createdAt: new Date().toISOString(),
        }),
      })

      if (!resp.ok) throw new Error(`Request failed: ${resp.status}`)

      ElMessage.success('Thanks! Your message has been sent.')
      resetForm()
    } catch (e) {
      ElMessage.error('Sorry, sending failed. Please email info@pillarenergy.com.au.')
    } finally {
      sending.value = false
    }
  })
}

/**
 * Highlight active section on scroll (simple approach)
 */
const sections: NavKey[] = ['home', 'about', 'services', 'projects', 'contact', 'zh']
if (typeof window !== 'undefined') {
  window.addEventListener(
    'scroll',
    () => {
      const y = window.scrollY + 120
      for (let i = sections.length - 1; i >= 0; i--) {
        const key = sections[i]
        const el = document.getElementById(ids[key])
        if (!el) continue
        if (y >= el.offsetTop) {
          active.value = key
          break
        }
      }
    },
    { passive: true }
  )
}
</script>

<style scoped>
/* Energy theme: light + green/blue accents */
.app-shell {
  min-height: 100vh;
  background: radial-gradient(1200px 600px at 20% -10%, rgba(36, 196, 155, 0.14), transparent 60%),
    radial-gradient(1000px 500px at 90% 0%, rgba(41, 127, 255, 0.12), transparent 55%),
    #f7fafc;
  color: #0f172a;
}

/* Header */
.app-header {
  position: sticky;
  top: 0;
  z-index: 20;
  display: flex;
  align-items: center;
  gap: 16px;
  height: 72px;
  border-bottom: 1px solid rgba(15, 23, 42, 0.08);
  background: rgba(255, 255, 255, 0.78);
  backdrop-filter: blur(10px);
}

.brand {
  display: flex;
  align-items: center;
  gap: 12px;
  cursor: pointer;
  user-select: none;
  min-width: 280px;
}

.brand-mark {
  width: 42px;
  height: 42px;
  border-radius: 12px;
  display: grid;
  place-items: center;
  font-weight: 800;
  color: #0b1220;
  background: linear-gradient(135deg, rgba(36, 196, 155, 0.35), rgba(41, 127, 255, 0.28));
  border: 1px solid rgba(15, 23, 42, 0.08);
}

.brand-name {
  font-weight: 800;
  letter-spacing: 0.6px;
}

.brand-sub {
  font-size: 12px;
  color: rgba(15, 23, 42, 0.64);
  margin-top: 2px;
}

.top-menu {
  flex: 1;
  border-bottom: none;
  background: transparent;
}

.header-actions {
  display: flex;
  align-items: center;
  gap: 12px;
}

.cta {
  border-radius: 12px;
}

/* Main */
.app-main {
  padding: 0;
}

.section {
  max-width: 1120px;
  margin: 0 auto;
  padding: 56px 16px;
}

.section-head {
  margin-bottom: 18px;
}

.section-title {
  margin: 0;
  font-size: 48px;
  letter-spacing: -0.3px;
}

.section-sub {
  margin: 8px 0 0 0;
  color: rgba(15, 23, 42, 0.68);
  line-height: 1.6;
}

/* Hero */
.hero {
  padding-top: 44px;
  padding-bottom: 44px;
  position: relative;
}

.hero-bg {
  position: absolute;
  inset: 0;
  border-bottom: 1px solid rgba(15, 23, 42, 0.06);
  background:
    radial-gradient(700px 280px at 15% 25%, rgba(36, 196, 155, 0.18), transparent 60%),
    radial-gradient(700px 280px at 85% 20%, rgba(41, 127, 255, 0.16), transparent 62%),
    linear-gradient(180deg, rgba(255, 255, 255, 0.65), rgba(255, 255, 255, 0));
  pointer-events: none;
}

.hero-row {
  position: relative;
  z-index: 1;
}

.hero-kicker {
  font-size: 16px;
  font-weight: 700;
  color: rgba(15, 23, 42, 0.7);
  letter-spacing: 0.8px;
  text-transform: uppercase;
  margin-bottom: 10px;
}

.hero-title {
  margin: 0;
  font-size: 46px;
  line-height: 1.06;
  letter-spacing: -1px;
}

.hero-title-brand {
  display: block;
}

.hero-title-line {
  display: block;
  margin-top: 10px;
  background: linear-gradient(90deg, #0f172a, rgba(15, 23, 42, 0.64));
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}

.hero-desc {
  margin: 16px 0 0 0;
  font-size: 16px;
  color: rgba(15, 23, 42, 0.72);
  line-height: 1.7;
  max-width: 58ch;
}

.hero-actions {
  display: flex;
  gap: 12px;
  margin-top: 18px;
  flex-wrap: wrap;
}

.hero-note {
  display: inline-flex;
  align-items: center;
  gap: 10px;
  margin-top: 14px;
  color: rgba(15, 23, 42, 0.62);
  font-size: 14px;
}

.dot {
  width: 10px;
  height: 10px;
  border-radius: 999px;
  background: linear-gradient(135deg, rgba(36, 196, 155, 0.95), rgba(41, 127, 255, 0.9));
}

/* Cards */
.card {
  border-radius: 16px;
  border: 1px solid rgba(15, 23, 42, 0.08);
}

.hero-card {
  border-radius: 18px;
  border: 1px solid rgba(15, 23, 42, 0.08);
  background: rgba(255, 255, 255, 0.7);
}

.card-header {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
}

.p {
  margin: 0 0 10px 0;
  line-height: 1.75;
}

.muted {
  color: rgba(15, 23, 42, 0.65);
}

.pill-grid {
  margin-top: 12px;
}

.pill {
  border-radius: 14px;
  border: 1px solid rgba(15, 23, 42, 0.08);
  background: rgba(255, 255, 255, 0.78);
}

.pill-title {
  font-weight: 800;
}

.pill-desc {
  margin-top: 6px;
  font-size: 12px;
  color: rgba(15, 23, 42, 0.62);
  line-height: 1.5;
}

.mini {
  border-radius: 14px;
  border: 1px solid rgba(15, 23, 42, 0.08);
  background: rgba(255, 255, 255, 0.82);
}

.mini-title {
  font-weight: 800;
}

.mini-desc {
  margin-top: 6px;
  font-size: 12px;
  color: rgba(15, 23, 42, 0.62);
  line-height: 1.5;
}

.tag-block {
  width: 100%;
  padding: 10px 12px;
  border-radius: 12px;
  justify-content: flex-start;
}

/* Projects */
.project {
  border-radius: 14px;
  border: 1px solid rgba(15, 23, 42, 0.08);
  background: rgba(255, 255, 255, 0.82);
  margin-bottom: 10px;
}

.project-top {
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 10px;
  margin-bottom: 8px;
}

.project-name {
  font-weight: 800;
}

.project-meta {
  font-size: 13px;
  color: rgba(15, 23, 42, 0.68);
  display: grid;
  gap: 6px;
}

.k {
  font-weight: 700;
  color: rgba(15, 23, 42, 0.75);
  margin-right: 6px;
}

/* Contact */
.contact-form :deep(.el-form-item__label) {
  font-weight: 700;
}

.form-actions {
  display: flex;
  justify-content: flex-end;
  gap: 10px;
  margin-top: 10px;
}

.form-hint {
  margin: 12px 0;
}

.info-list {
  display: grid;
  gap: 12px;
}

.info-item {
  display: grid;
  gap: 4px;
}

.info-k {
  font-size: 12px;
  font-weight: 800;
  color: rgba(15, 23, 42, 0.6);
  text-transform: uppercase;
  letter-spacing: 0.6px;
}

.info-v {
  font-size: 14px;
}

/* Footer */
.app-footer {
  border-top: 1px solid rgba(15, 23, 42, 0.08);
  background: rgba(255, 255, 255, 0.75);
  backdrop-filter: blur(8px);
}

.footer-inner {
  max-width: 1120px;
  margin: 0 auto;
  padding: 18px 16px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 14px;
}

.footer-brand {
  font-weight: 900;
  letter-spacing: 0.6px;
}

.footer-meta {
  margin-top: 6px;
  color: rgba(15, 23, 42, 0.62);
  font-size: 13px;
}

@media (max-width: 900px) {
  .brand {
    min-width: auto;
  }
  .brand-sub {
    display: none;
  }
  .hero-title {
    font-size: 38px;
  }
}
</style>
