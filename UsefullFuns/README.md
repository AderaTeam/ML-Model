# mod_user_for_predict
```mod_user_for_predict(a, gdps, space, classificator, create_vector_user)``` - создаёт вектор клиента, где
- 1 параметр вектора - это класс юзера;
- 2-100 - npo_sum по времени уравновешанные фильтром;
- 101-201 - значения ВВП в данный период.
## Параметры
- a - датафрейм из истории юзера;
- gdps - датафрейм ВВП со столбцами:
    - month - месяц;
    - year - год;
    - gdv - значение ВВП в млн. руб.
- classificator - классификатор для пользователя;
- create_vector_user - векторизатор пользователя.


# create_vector_user
```create_vector_user(user_table)``` - приходит, датафрейм с историей операций одного юзера полученного по npo_accnt_id, полученного из all_in_one (объединения всего), возвращает вектор из 40 объектов:
- 'freq' - частота, сколько выплат было,
- 'npo_sum_mean' - среднее по выплатам, 
- 'npo_sum_std' - среднее квадратичное откланение по выплатам, 
- 'npo_sum_min' - минимальная плата, 
- 'npo_sum_max' - максимальная плата, 
### Данные константные для юзера
'npo_operation_group_mean', 
'npo_operation_group_std', 
'npo_operation_group_min', 
'npo_operation_group_max', 
'npo_operation_date_year_mean', 
'npo_operation_date_year_std', 
'npo_operation_date_year_min', 
'npo_operation_date_year_max', 
'npo_operation_date_month_mean', 
'npo_operation_date_month_std', 
'npo_operation_date_month_min', 
'npo_operation_date_month_max',
'npo_operation_date_day_mean', 
'npo_operation_date_day_std', 
'npo_operation_date_day_min', 
'npo_operation_date_day_max',
'accnt_pnsn_schm',
'npo_accnt_status', 
'npo_blnc', 
'npo_pmnts_sum', 
'npo_pmnts_nmbr',
'npo_ttl_incm', 
'npo_accnt_status_date_year',
'npo_accnt_status_date_month', 
'npo_accnt_status_date_day',
'npo_frst_pmnt_date_year', 
'npo_frst_pmnt_date_month',
'npo_frst_pmnt_date_day', 
'npo_lst_pmnt_date_year',
'npo_lst_pmnt_date_month', 
'npo_lst_pmnt_date_day', 
'gndr', 
'brth_yr',
'pstl_code', 'city'