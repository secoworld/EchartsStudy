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
   * `series`: 系列列表。每个系列通过 type 决定自己的图表类型
     * `bar`: 柱状/条形图
     * `pie`: 饼状图
     * `line`: 折线图/面积图
     * `scatter`: 散点/气泡图
     * `effectScatter`: 动态气泡图
     * `radar`: 雷达图主要用于表现多变量的数据，例如球员的各个属性分析
     * `tree`: 树图主要用来可视化树形数据结构，是一种特殊的层次类型，具有唯一的根节点，左子树，和右子树。
     * `treemap`: Treemap 是一种常见的表达『层级数据』『树状数据』的可视化形式。它主要用面积的方式，便于突出展现出『树』的各层级中重要的节点。
     * `sunburst`: 旭日图（Sunburst）由多层的环形图组成，在数据结构上，内圈是外圈的父节点。因此，它既能像饼图一样表现局部和整体的占比，又能像矩形树图一样表现层级关系。
     * `candlestick`: Candlestick 即我们常说的 K线图。
     * `heatmap`: 热力图主要通过颜色去表现数值的大小，必须要配合 visualMap 组件使用。
     * `map`: 地图主要用于地理区域数据的可视化，配合 visualMap 组件用于展示不同区域的人口分布密度等数据。
     * `parallel`: 平行坐标系的系列。
     * `lines`: 用于带有起点和终点信息的线数据的绘制，主要用于地图上的航线，路线的可视化。
     * `graph`: 用于展现节点以及节点之间的关系数据。
     * `sankey`: 是一种特殊的流图（可以看作是有向无环图）。 它主要用来表示原材料、能量等如何从最初形式经过中间过程的加工或转化达到最终状态。
     * `funnel`: 漏斗图
     * `gauge`: 仪表盘
     * `pictorialBar`: 象形柱图是可以设置各种具象图形元素（如图片、SVG PathData 等）的柱状图。往往用在信息图中。用于有至少一个类目轴或时间轴的直角坐标系上。
     * `themeRiver`: 主题河流 是一种特殊的流图, 它主要用来表示事件或主题等在一段时间内的变化。
     * `custom`: 自定义系列可以自定义系列中的图形元素渲染。从而能扩展出不同的图表。


    更多相关的配置，可以到[配置项option](https://echarts.baidu.com/option.html)中进行查找
   