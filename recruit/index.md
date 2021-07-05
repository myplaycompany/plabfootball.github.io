---
layout: main
main: true
recruit: true
title: 채용정보
---

<div class="loading-animation">
    <div class="recruit">
        <div class="section want">
            <div class="title">이렇게 나아갈게요</div>
             <div class="content">
                <ul>
                    <li>좋은 팀, 좋은 프로덕트를 만들기 위해 함께 고민하고 성장합니다</li>
                    <li>현재의 실력보다 앞으로의 가능성에 대해 이야기하고 응원합니다</li>
                    <li>각자의 경험과 개성을 존중합니다</li>
                    <li>향후 본인의 선호와 기량에 따라 백엔드, 플랫폼, 인프라 등 직무를 변경할 수 있는 유연한 업무 환경을 구축하고 있습니다.</li>
                </ul>
            </div>
        </div>
        <div class="section position">
            <div class="title">플랩풋볼과 함께 할 동료를 찾고 있습니다</div>
            <div class="content">
                {% assign positions = site.data.recruit-position %}
                {% if positions.size > -1 %}
                <div class="catalogue">
                    {% for position in positions %}
                    <div class="catalogue-item">
                        <div class="catalogue-title transition">
                            <div class="content-wrap">
                                <div class="name">{{position.name}}</div>
                                <div class="description">{{position.title}}</div>
                            </div>
                            <div class="icon"><div></div></div>
                        </div>
                        <div class="catalogue-body">
                            {% if position.position != null %}
                            <div class="item position">
                                <div class="title">👤 포지션 소개</div>
                                <ul class="position">
                                    {% for position in position.position %}
                                    <li>{{position}}</li>
                                    {% endfor %}
                                </ul>
                            </div>
                            {% endif %}
                            <div class="item overview">
                                <div class="title">💻 하시게 될 업무</div>
                                <ul class="overview">
                                    {% for overview in position.overview %}
                                    {% if overview.main != null %}
                                    <li>{{overview.main}}</li>
                                    {% for overview in position.overview %}
                                    <li class="sub">{{overview.sub}}</li>
                                    {% endfor %}
                                    {% else %}
                                    <li>{{overview}}</li>
                                    {% endif %}
                                    {% endfor %}
                                </ul>
                            </div>
                            <div class="item requirements">
                                <div class="title">🙋 아래 기준에 맞는 분을 찾습니다</div>
                                <ul class="requirement">
                                    {% for requirement in position.requirement %}
                                    <li>{{requirement}}</li>
                                    {% endfor %}
                                </ul>
                            </div>
                            <div class="item useful">
                                <div class="title">💪 이런 분이면 더욱 좋습니다</div>
                                <ul class="useful">
                                    {% for useful in position.useful %}
                                    <li>{{useful}}</li>
                                    {% endfor %}
                                </ul>
                            </div>
                            <div class="item useful">
                                <div class="title">⚙️ 인프라</div>
                                <ul class="useful">
                                    {% for infra in position.infra %}
                                    <li>{{infra}}</li>
                                    {% endfor %}
                                </ul>
                            </div>
                            <div class="footer">
                                <div class="blank"></div>
                                <a href="{{position.url}}" class="button transition" target='_blank'>지원하기</a>
                            </div>
                        </div>
                    </div>
                    {% endfor %}
                </div>
                {% else %}
                    <div class="recruit-draft-message">
                        <h1>
                            &#x1F64B; Coming Soon!
                        </h1>
                    </div>
                {% endif %}
            </div>
        </div>
        <div class="section process">
            <div class="title">채용 프로세스</div>
            <div class="list">
                {% for process in site.data.recruit-process %}
                <li>{{process.label}}</li>
                {% endfor %}
            </div>
        </div>
        <!-- <div class="section process">
            <div class="title">상시 채용 프로세스</div>
            <div class="content">
                <div class="list">
                    {% for process in site.data.recruit-process %}
                    <div class="process-item">
                        <div class="circle {% if process.detail != nil %}has-detail{% endif %}">
                            <div class="text-wrapper">
                                <div class="index">0{{process.index}}</div>
                                <div class="label">{{process.label}}</div>
                                {% if process.detail != nil %}
                                <ul class="detail">
                                    {% for detail in process.detail %}
                                    <li>{{ detail }}</li>                            
                                    {% endfor %}
                                </ul>
                                {% endif %}
                            </div>
                        </div>
                        <div class="description">
                            {{process.description}}
                        </div>
                    </div>
                    {% endfor %}
                </div>
            </div>
        </div> -->
        <div class="section welfare culture">
            <div class="title">개발팀 문화</div>
            <div class="content">
                <div class="card-list">
                    {% for welfare in site.data.welfares %}
                    {% if welfare.type == 'dev' %}
                    <div class="card">
                        <div class="title">
                            <span class="emoji">{{welfare.emoji}}</span>
                            {{welfare.title}}
                        </div>
                        <div class="subtitle">{{welfare.subtitle}}</div>
                        <div class="description">
                            <ul>
                                {% for description in welfare.description %}
                                <li class="item">{{description}}</li>
                                {% endfor %}
                            </ul>
                        </div>
                    </div>
                    {% endif %}
                    {% endfor %}   
                </div>  
            </div>
        </div>
        <div class="section welfare">
            <div class="title">사내 복지제도</div>
            <div class="content">
                <div class="card-list">
                    {% for welfare in site.data.welfares %}
                    {% if welfare.type == 'all' %}
                    <div class="card">
                        <div class="title">
                            <span class="emoji">{{welfare.emoji}}</span>
                            {{welfare.title}}
                        </div>
                        <div class="subtitle">{{welfare.subtitle}}</div>
                        <div class="description">
                            <ul>
                                {% for description in welfare.description %}
                                <li class="item">{{description}}</li>
                                {% endfor %}
                            </ul>
                        </div>
                    </div>
                    {% endif %}
                    {% endfor %}   
                </div>  
            </div>
        </div>
    </div>
</div>

<script>
    $('.catalogue-title').click(function() {
        if ($(this).parent().hasClass('visible')) {
            $(this).parent().removeClass('visible');
        } else {
            $(this).parent().addClass('visible');
        }
    });
</script>
