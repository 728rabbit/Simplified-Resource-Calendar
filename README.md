# Simplified-Resource-Calendar

const resources = [
    { id: 1, name: '會議室 A' },
    { id: 2, name: '會議室 B' },
    { id: 3, name: '會議室 C' },
    { id: 4, name: '會議室 D' },
    { id: 5, name: '會議室 E' },
];

const events = [
    { resourceId: 1, startHm: 815, endHm: 950, content: '08:15 ~ 09:50', background: '#FFA726' },
    { resourceId: 2, startHm: 1000, endHm: 2200, content: '10:00 ~ 22:00', background: '#2A9D8F' },
    { resourceId: 3, startHm: 1330, endHm: 1430, content: '13:30 ~ 14:30' },
    { resourceId: 1, startHm: 915, endHm: 1045, content: '09:15 ~ 10:45', background: '#4C7B96' },
    { resourceId: 2, startHm: 1000, endHm: 1430, content: '10:00 ~ 14:30' },
];
const icalendar = new iCalendar({ startHm: 800, endHm: 2200, interval: 5, maxHeight: 480 });
icalendar.initialize(resources);
icalendar.drawEvents(events);
