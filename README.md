# 🌏 세계 발전과 빈곤 프로젝트 
World Development and Poverty Project

## 프로젝트 개요
1, 2편으로 나누어진 이 프로젝트는 Gapminder.org에서 제공하는 데이터를 활용하여 전 세계적인 인구 성장과 국가별 빈곤 문제에 초점을 맞추어 비교 분석하는 프로젝트 였습니다. 

특히 각 국가의 인구 성장률과 빈곤률의 변화를 이해하고, 이러한 변화가 세계 발전에 어떠한 영향을 미치는지에 대하여, 데이터를 통해 인과관계를 분석하고 이해하고자 하였습니다.

## 사용된 도구
- Python
- Datascience 라이브러리
- NumPy
- Matplotlib

## 주요 기능
- **데이터 처리 및 분석**: 각 국가의 인구 데이터와 빈곤률을 시간에 따라 분석하여, **경향성과 패턴**을 식별
- **시각화**: 인구 성장률과 빈곤률의 변화를 그래프로 시각화하여 비교 분석
- **계산식 개발**: 인구 성장률과 빈곤률 계산을 위한 수학적 모델을 구현하고 적용
    ```python
    def calculate_growth_rate(initial_value, final_value, years):
        return (final_value - initial_value) / initial_value / years

    data = pd.read_csv('gapminder_data.csv')
    initial_pop = data[data['year'] == 1960]['population']
    final_pop = data[data['year'] == 2020]['population']
    years = 2020 - 1960
    growth_rate = calculate_growth_rate(initial_pop, final_pop, years)
    print(f"Average Annual Growth Rate: {growth_rate:.2%}")
    ```
- **국가별 비교 분석**: 다양한 국가의 데이터를 비교를 통해, 전 세계적인 경향과 특정 국가의 상황을 이해
    ```python
    countries = ['United States', 'India', 'China']
    for country in countries:
        country_data = data[data['country'] == country]
        initial_pop = country_data[country_data['year'] == 1960]['population'].values[0]
        final_pop = country_data[country_data['year'] == 2020]['population'].values[0]
        growth_rate = calculate_growth_rate(initial_pop, final_pop, years)
        print(f"{country}: {growth_rate:.2%}")
    ```

## 결과
인도, 중국, 미국등 다양한 나라의 지표들을 시각화하여 성장률과 빈곤률의 추세를 시간대 별로 분석, 비교하였습니다.
