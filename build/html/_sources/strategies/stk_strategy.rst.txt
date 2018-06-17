
.. _strategy-stk:

==================
股票策略
==================

点击菜单“数据”->“选股&策略编辑管理”，弹出对话框，如下图：

    .. image:: /_static/images/strategy_dlg.png
        :align: center

点开左侧策略图标，展开树目录，会看到已有的交易策略，可以新增交易策略。选股在“用途”设置项必须设置成“策略”。


下面是一些股票策略的JSON格式数据：

    * STK-BK-BUL-D

    .. code:: java

        {
        "barsize" : 7,
        "expr0" : "cross_up(TYPICAL_PRICE,SQUEEZE_BAND_UPL) and factor(SQUEEZE_GAP)>0.618",
        "expr1" : "(COST_X_ATR<-2*STDDEV_ATR and factor(TL_FAST)<0) or (COST_X_ATR>0.4 and COST_X_ATR+MAXDOWN_ATR>STDDEV_ATR and (COST_X_ATR<1.6*MAXDOWN_ATR or MAXDOWN_ATR>STDDEV_ATR) and factor(LR_SLOPE_FAST)<factor(LR_SLOPE_SLOW_THRESHOLD) and factor(LR_SLOPE_MIDD)<factor(LR_SLOPE_FAST_THRESHOLD)) or (COST_X_ATR>3*STDDEV_ATR and MAXDOWN_ATR>0.6 and factor_prev(LR_SLOPE_FAST)>factor(LR_SLOPE_FAST))",
        "expr2" : "cross_down(LR_SLOPE_FAST,LR_SLOPE_FAST_THRESHOLD)",
        "expr3" : "",
        "expr4" : "COST_X_ATR>4 and MAXDOWN_ATR>0.618",
        "group" : 15,
        "id" : "06160920101246000",
        "name" : "STK-BK-BUL-D",
        "remark" : "",
        "used" : "策略"
        }


