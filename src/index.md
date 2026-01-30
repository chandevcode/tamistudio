---
layout: default
title: home
---
  <p class="max-w-xl text-center text-gray-300 leading-relaxed mb-8">
    Building SaaS and internal tools.  
    Ruby on Rails developer.  
    Exploring quiet, sustainable software businesses.
  </p>

  <!-- Subscribe -->
  <div class="w-full max-w-md mb-16">
    <div class="join w-full">
      <input
        type="email"
        placeholder="Type your email…"
        class="input input-bordered join-item text-neutral w-full bg-base-200"
      />
      <button class="btn join-item btn-neutral bg-gray-800 hover:bg-gray-700 text-white">
        Subscribe
      </button>
    </div>
  </div>

<div class="w-full max-w-3xl">
  <% collections.posts.resources
     .sort_by { |p| p.data.date }
     .reverse
     .first(1)
     .each do |post| %>

    <div class="card bg-base-100 border border-base-300">
      <div class="card-body">

        <p class="text-sm text-gray-900 mb-2">
          <%= post.data.date.strftime("%B %-d, %Y") %>
        </p>

        <h2 class="card-title text-2xl font-semibold text-gray-900 mb-2">
          <%= post.data.title %>
        </h2>

        <p class="text-base-content/80">
          <%= post.data.description || post.excerpt %>
        </p>

        <div class="mt-4">
          <a href="<%= post.relative_url %>" class="link link-hover text-sm text-gray-900 font-medium">
            Read more →
          </a>
        </div>

      </div>
    </div>
  <% end %>

