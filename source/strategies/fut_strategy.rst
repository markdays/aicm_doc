
.. _strategy-fut:

==================
期货策略
==================

点击菜单“数据”->“选股&策略编辑管理”，弹出对话框，如下图：

    .. image:: /_static/images/strategy_dlg.png
        :align: center

点开左侧策略图标，展开树目录，会看到已有的交易策略，可以新增交易策略。选股在“用途”设置项必须设置成“策略”。

期货策略通常是由一个多头策略和一个空头策略组成，当然只设置其中一个也可以。

下面是一些期货策略的JSON格式数据：

    * FUT-AW-R-LONG

    .. code:: java

        {
        "barsize" : 6,
        "expr0" : "(entry_signal(td_long,ent_lrs_fast) or entry_signal(td_long,ent_hyo_over)) and  factor(TATR)/factor(CLOSE)>0.0025 and trend_level(fd_main,tl_stddev)>=2 and factor(TL_FAST)>0",
        "expr1" : "(trend_level(fd_main,tl_stddev)<=2 and stop_profit(td_long, sp_trace,0.5)) or (trend_level(fd_main,tl_stddev)>2 and stop_profit(td_long,sp_maxdown,1)) or stop_loss(td_long,sl_mult_stddev,3)",
        "expr2" : "(trend_level(fd_main,tl_stddev)<=2 and exit_signal(td_long, ext_lrs_fast)) or (trend_level(fd_main,tl_stddev)>2 and exit_signal(td_long, ext_hyo_cross))",
        "expr3" : "",
        "expr4" : "",
        "group" : 80,
        "id" : "00180403222144000",
        "name" : "FUT-AW-R-LONG",
        "remark" : "",
        "used" : "策略"
        }


    * FUT-AW-R-SHORT

    .. code:: java

        {
        "barsize" : 6,
        "expr0" : "(entry_signal(td_short,ent_lrs_fast) or entry_signal(td_short,ent_hyo_over)) and  factor(TATR)/factor(CLOSE)>0.0025 and trend_level(fd_main,tl_stddev)>=2 and factor(TL_FAST)<0",
        "expr1" : "(trend_level(fd_main,tl_stddev)<=2 and stop_profit(td_short, sp_trace,0.5)) or (trend_level(fd_main,tl_stddev)>2 and stop_profit(td_short,sp_maxdown,1)) or stop_loss(td_short,sl_mult_stddev,3)",
        "expr2" : "(trend_level(fd_main,tl_stddev)<=2 and exit_signal(td_short, ext_lrs_fast)) or (trend_level(fd_main,tl_stddev)>2 and exit_signal(td_short, ext_hyo_cross))",
        "expr3" : "",
        "expr4" : "",
        "group" : 80,
        "id" : "00180403222300001",
        "name" : "FUT-AW-R-SHORT",
        "remark" : "",
        "used" : "策略"
        }

