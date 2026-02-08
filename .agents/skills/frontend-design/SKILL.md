---
name: frontend-design
description: Create distinctive, production-grade frontend interfaces with high design quality. Use this skill when the user asks to build web components, pages, artifacts, posters, or applications (examples include websites, landing pages, dashboards, React components, HTML/CSS layouts, or when styling/beautifying any web UI). Generates creative, polished code and UI design that avoids generic AI aesthetics.
license: Complete terms in LICENSE.txt
---

This skill guides creation of distinctive, production-grade frontend interfaces that avoid generic "AI slop" aesthetics. Implement real working code with exceptional attention to aesthetic details and creative choices.

The user provides frontend requirements: a component, page, application, or interface to build. They may include context about the purpose, audience, or technical constraints.

## Design Thinking

Before coding, understand the context and commit to a BOLD aesthetic direction:
- **Purpose**: What problem does this interface solve? Who uses it?
- **Tone**: Pick an extreme: brutally minimal, maximalist chaos, retro-futuristic, organic/natural, luxury/refined, playful/toy-like, editorial/magazine, brutalist/raw, art deco/geometric, soft/pastel, industrial/utilitarian, etc. There are so many flavors to choose from. Use these for inspiration but design one that is true to the aesthetic direction.
- **Constraints**: Technical requirements (framework, performance, accessibility).
- **Differentiation**: What makes this UNFORGETTABLE? What's the one thing someone will remember?

**CRITICAL**: Choose a clear conceptual direction and execute it with precision. Bold maximalism and refined minimalism both work - the key is intentionality, not intensity.

Then implement working code (HTML/CSS/JS, React, Vue, etc.) that is:
- Production-grade and functional
- Visually striking and memorable
- Cohesive with a clear aesthetic point-of-view
- Meticulously refined in every detail

## Frontend Aesthetics Guidelines

Focus on:
- **Typography**: Choose fonts that are beautiful, unique, and interesting. Avoid generic fonts like Arial and Inter; opt instead for distinctive choices that elevate the frontend's aesthetics; unexpected, characterful font choices. Pair a distinctive display font with a refined body font.
- **Color & Theme**: Commit to a cohesive aesthetic. Use CSS variables for consistency. Dominant colors with sharp accents outperform timid, evenly-distributed palettes.
- **Motion**: Use animations for effects and micro-interactions. Prioritize CSS-only solutions for HTML. Use Motion library for React when available. Focus on high-impact moments: one well-orchestrated page load with staggered reveals (animation-delay) creates more delight than scattered micro-interactions. Use scroll-triggering and hover states that surprise.
- **Spatial Composition**: Unexpected layouts. Asymmetry. Overlap. Diagonal flow. Grid-breaking elements. Generous negative space OR controlled density.
- **Backgrounds & Visual Details**: Create atmosphere and depth rather than defaulting to solid colors. Add contextual effects and textures that match the overall aesthetic. Apply creative forms like gradient meshes, noise textures, geometric patterns, layered transparencies, dramatic shadows, decorative borders, custom cursors, and grain overlays.

NEVER use generic AI-generated aesthetics like overused font families (Inter, Roboto, Arial, system fonts), cliched color schemes (particularly purple gradients on white backgrounds), predictable layouts and component patterns, and cookie-cutter design that lacks context-specific character.

Interpret creatively and make unexpected choices that feel genuinely designed for the context. No design should be the same. Vary between light and dark themes, different fonts, different aesthetics. NEVER converge on common choices (Space Grotesk, for example) across generations.

**IMPORTANT**: Match implementation complexity to the aesthetic vision. Maximalist designs need elaborate code with extensive animations and effects. Minimalist or refined designs need restraint, precision, and careful attention to spacing, typography, and subtle details. Elegance comes from executing the vision well.

Remember: Claude is capable of extraordinary creative work. Don't hold back, show what can truly be created when thinking outside the box and committing fully to a distinctive vision.

## Component Markup Convention

모든 의미 있는 UI 컴포넌트에 `data-component` 속성을 반드시 추가한다. 이 속성은 design_agent가 컴포넌트를 자동 인식하는 데 사용된다.

**대상 컴포넌트 타입과 값:**

| 타입 | `data-component` 값 | 대상 |
|------|---------------------|------|
| card | `card` | 카드, 타일, 패널 등 콘텐츠 컨테이너 |
| badge | `badge` | 뱃지, 태그, 칩, 상태 라벨 |
| alert | `alert` | 알림, 토스트, 노티스 배너 |
| modal | `modal` | 모달, 다이얼로그, 바텀시트 |
| tab | `tab` | 탭 그룹 컨테이너 |
| stat | `stat` | 통계 카드, KPI 위젯 |

**HTML 태그로 이미 구분되는 요소(`<button>`, `<input>`, `<table>`, `<nav>`)에는 추가하지 않는다.**

예시:
```html
<!-- 카드 -->
<div data-component="card" class="bg-white rounded-lg shadow-md p-6">
  <h3>제목</h3>
  <p>내용</p>
</div>

<!-- 뱃지 -->
<span data-component="badge" class="bg-emerald-100 text-emerald-700 text-xs px-2 py-0.5 rounded-full">활성</span>

<!-- 통계 카드 -->
<div data-component="stat" class="bg-white rounded-xl p-4 shadow-sm">
  <div class="text-2xl font-bold">1,234</div>
  <div class="text-sm text-gray-500">총 사용자</div>
</div>

<!-- 알림 -->
<div data-component="alert" class="bg-amber-50 border border-amber-200 rounded-lg p-4">
  <p>경고 메시지</p>
</div>
```
