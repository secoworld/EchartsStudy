## lesson1 初试Ecahrts

尝试Echarts的图形
1. 首先需要引入`echarts.min.js`，可以在官网上下载，或者直接使用`cdn`文件，可以在`bootcdn.cn`中找到
   ```
   <script src="https://cdn.bootcss.com/echarts/4.2.1-rc1/echarts.min.js"></script>
   ```
2. 在`html`文档中创建一个`div`,指定宽度和高度
   ```
   <!-- 创建一个适合大小的Dom -->
    <div id="main" style="width: 600px; height: 400px;"></div>
   ```
3. 在`script`标签中书写echarts相关内容：    
   首先对`echarts`进行初始化，将上面创建的`div`的文件传入
   ```
    var myChart = echarts.init(document.getElementById("main"));
   ```

   然后设置`setOption`中的传入的参数`option`
   ```
   // 设置选项
        var option = {
            // 显示的标题
            title: {
                text: "Echarts入门展示"
            },
            // 提示框组件
            tooltip:{},
            // 图例说明
            legend: {
                data: ['销量'],
                // 对其方式
                align: 'left'
            },
            // x轴显示的数据
            xAxis: {
                data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
            },
            // y轴显示的数据
            yAxis: {},
            // 显示的数据
            series: [{
                name: "销量",
                // 设置图形的类型， bar:柱状图， line：折线图， pie：饼状图
                type: 'bar',
                data: [5, 20, 36, 10, 10, 20]
            }],
        };
   ```

   最后将上面的内容进行展示
   ```
    myChart.setOption(option);
   ```

4. `option`中的内容详解
   