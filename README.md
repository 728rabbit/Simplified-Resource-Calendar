# Simplified-Resource-Calendar

// Usage Example
const resources = [
    { id: 1, name: '會議室 A' },
    { id: 2, name: '會議室 B' },
    { id: 3, name: '會議室 C' },
    { id: 4, name: '會議室 D' },
    { id: 5, name: '會議室 E' }
];

const events = [
    { resourceId: 1, targetDate: '2024-09-03', startHm: 715, endHm: 950, content: '07:15 ~ 09:50', background: '#FFA726' },
    { resourceId: 1, targetDate: '2024-09-04', startHm: 815, endHm: 950, content: '08:15 ~ 09:50', background: '#FFA156' },
    { resourceId: 2, targetDate: '2024-09-03', startHm: 1000, endHm: 2250, content: '10:00 ~ 22:50', background: '#2A9D8F' },
    { resourceId: 3, targetDate: '2024-09-03', startHm: 1330, endHm: 1430, content: '13:30 ~ 14:30' },
    { resourceId: 1, targetDate: '2024-09-03', startHm: 915, endHm: 1045, content: '09:15 ~ 10:45', background: '#4C7B96' },
    { resourceId: 2, targetDate: '2024-09-03', startHm: 1000, endHm: 1430, content: '10:00 ~ 14:30' },
];

const icalendar = new iCalendar({
    lang: 'zh',
    displayMode: 'week', 
    date: '2024-09-02', 
    startHm: 800, 
    endHm: 2200, 
    interval: 5, 
    maxHeight: 680,
    resources: 'http://localhost/mylib/testsource.php?index=1',
    events: 'http://localhost/mylib/testsource.php?index=2',
    eventsTemplate: function(data) {
        return 'T:' + data['content'];
    },
    eventsClick: function(data) {
        console.log(data);
    },
    extraParas: 
    {
        resource_id: 1 
    }
});
icalendar.init(resources, events);
