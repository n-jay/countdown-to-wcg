---
title: progress
---

<link rel="stylesheet" href="assets/css/frappe-gantt.css" />
<script src="assets/js/frappe-gantt.min.js"></script>

<section>
    <center><h4>Work done and work left to do...</h4></center>

    <center><svg id="gantt"></svg></center>
</section>

<section>
    <h4>Objectives to be completed</h4>
	<ul>
		<li>Finalize song 1</li>
		<li>Complete auditions for song 3</li>
		<li>Search for sponsorships</li>
	</ul>
</section>

<script>
    var tasks = [
			{
				start: '2020-10-01',
				end: '2020-10-08',
				name: 'Task 1',
				id: "Task 0",
				progress: 20
			},
			{
				start: '2020-10-03',
				end: '2020-10-06',
				name: 'Task 2',
				id: "Task 1",
				progress: 5,
				dependencies: 'Task 0'
			},
			{
				start: '2020-10-04',
				end: '2020-10-08',
				name: 'Task 3',
				id: "Task 2",
				progress: 10,
				dependencies: 'Task 1'
			},
			{
				start: '2020-10-08',
				end: '2020-10-09',
				name: 'Task 4',
				id: "Task 3",
				progress: 5,
				dependencies: 'Task 2'
			},
			{
				start: '2020-10-08',
				end: '2020-10-10',
				name: 'Task 5',
				id: "Task 4",
				progress: 0,
				dependencies: 'Task 2'
			},
			{
				start: '2020-10-11',
				end: '2020-10-11',
				name: 'Task 6',
				id: "Task 5",
				progress: 0,
				dependencies: 'Task 4',
				custom_class: 'bar-milestone'
			}
        ]
        
        var gantt = new Gantt("#gantt", tasks, {
            header_height: 50,
            column_width: 30,
            step: 24,
            view_modes: ['Quarter Day', 'Half Day', 'Day', 'Week', 'Month'],
            bar_height: 20,
            bar_corner_radius: 3,
            arrow_curve: 5,
            padding: 18,
            view_mode: 'Day',   
            date_format: 'YYYY-MM-DD',
            custom_popup_html: null
        });
</script>
