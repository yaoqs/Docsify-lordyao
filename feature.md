<div id="repos">
    <div class="dropdown" onmouseenter="showList('dropdown-a')"
        onmouseleave="showList('dropdown-a')">
        <a id="a" href="javascript:void(0)" class="dropbtn">&#9776; Repositories Pages</a>
        <div class="dropdown-content" id="dropdown-a">
            <script>
                function showList(id) {
                    var drop = document.getElementById(id);
                    if (drop.classList.contains('show')) {
                        drop.classList.remove('show');
                    } else {
                        drop.classList.add('show');
                    }
                }
                $(async function () {
                    $.ajax("https://api.github.com/users/yaoqs/repos",
                        await function (dataString) {
                            var da=d3.select("body").select("#dropdown-a").selectAll("a").data(dataString).enter().append("a").attr("target","_blank").style("padding-left","1em").text((rep)=>{return '§ ' + rep.full_name}).attr("href",(rep)=>{return "https://yaoqs.github.io/" + rep.name});
                        },
                        function () {
                            $("<div style='color:red;width: 9em;height: 2em;text-align: center;display: table-cell;vertical-align: middle;'>当前无网络</div>").appendTo($("#dropdown-a"));
                        });
                });
            </script>
        </div>
    </div>
</div>