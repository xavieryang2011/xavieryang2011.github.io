---
title: SpannableStringBuilder用法实践
date: 2017-06-16 17:22
tags: 工作
---

本篇主要讲一下的使用SpannableStringBuilder处理富文本时遇到人坑。

    public void updateVlsContent(ChiVoxResultBean info) {
        String content=mTvGymAudioContent.getText().toString();
        SpannableStringBuilder contentspan=new SpannableStringBuilder(content);
        int startIndex;
        int endIndex;
        //富文本处理
        for (int i = 0; i < info.mDetails.size(); i++) {
            ForegroundColorSpan fcs;
            ChiVoxResultBean.ChiVoxDetail detail = info.mDetails.get(i);
            //计算startIndex,endIndex
            startIndex=detail.mBeginIndex;
            endIndex=detail.mEndIndex;
            //判断颜色
            if(info.mLevel==3){
                fcs=new ForegroundColorSpan(getResources().getColor(R.color.color_13d295));
            }else if(info.overall==0){
                fcs=new ForegroundColorSpan(getResources().getColor(R.color.color_fe5857));
            }else if(detail.mIsFail){
                fcs=new ForegroundColorSpan(getResources().getColor(R.color.color_fe5857));
            }else{
                fcs=new ForegroundColorSpan(getResources().getColor(R.color.color_13d295));
            }

            contentspan.setSpan(fcs,startIndex,endIndex+1, Spanned.SPAN_INCLUSIVE_INCLUSIVE);
        }

        mTvGymAudioContent.setText(contentspan);
    }

上面代码，用做处理驰声接口返回单词录音结果标红逻辑，用到的主要方法是SpannableStringBuilder.setPan(fcs,startIndex,endIndex,type),着急是找对索引startIndex和endIndex.前期花了很多时间找索引，结果后来从驰声返回的接口中找到了，真是白费了不少功夫。涉及到第三方接口对接的，还是要多一块沟通，这样能节省不少时间成本，还能控制上线风险。
![](/image/doEficient.jpg)
