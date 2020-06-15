---
home: true
heroImage: assets/images/paramdigma-black-large.svg
actionText: Get started! →
actionLink: /introduction/
xfeatures:
  - title: Data Trees
    details: DataTrees in GH convey meaning. Learn how to interpret that meaning and create appropriate structures.
    link: /data-trees
  - title: Keeping it tidy
    details: GH definitions are made to be visually interpretable, but these tricks will make your (and your team's) life easier.
  - title: Advanced GH components
    details: Some of the most powerful GH components are also confusing. We demistify some of our favourite's.
  - title: Best Practices
    details: Many coding best practices can be directly applied to visual programming definitions, making them easier to interpret and mantain over time.
  - title: Teamwork
    details: Ever wondered how to collaborate in the development of GH definitions? Learn how data packs and version control can help your team.
  - title: Interoperability
    details: A lot has changed since Grasshopper was first introduced. Learn about Rhino.Inside and Rhino.Compute and how to leverage their power.
footer: 'MIT Licensed | Paramdigma.com — Computational Geometry Collective | Built with VuePress and ❤️'
---

<div class="features">
  <div class="feature" v-for="feat in $page.frontmatter.xfeatures">
    <h2><a :href="feat.link">{{ feat.title }}</a></h2>
    <p>{{ feat.details }}</p>
  </div>
</div>
