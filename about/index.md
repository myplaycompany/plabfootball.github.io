---
layout: main
main: true
title: 개발팀 소개
---

<div class="loading-animation">
    <div class="about">
        <div class="section">
            <div class="title list">개발자 소개</div>
            <div class="content">
                <ul>
                    {% assign members = site.data.members | sort: 'id' | where_exp: 'member', 'member.id != 834001' %}
                    {% assign team = site.data.members | where: 'id', '834001' | concat: members %}
                    {% for member in team %}
                        <li class="member_card">
                            <div class="thumbnail">
                                {% assign thumbnail = site.static_files | where: 'basename', member.id | first %}
                                <img class="profile" src="{{ thumbnail.path }}" />
                                <div class="emoji">
                                    <span>{{member.emoji}}</span>
                                </div>
                            </div>
                            <div class="info">
                                <div class="name">{{member.name}}</div>
                                <div class="description">{{member.comment}}</div>
                            </div>
                        </li>
                    {% endfor %}
                </ul>
            </div>
        </div>
    </div>
</div>
