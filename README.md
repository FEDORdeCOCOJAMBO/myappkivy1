# myappkivy1
from kivy.app import App
from kivy.uix.button import Button
from kivy.uix.label import Label
from kivy.uix.boxlayout import BoxLayout
from kivy.uix.screenmanager import ScreenManager, Screen
class MainScr(Screen):
    def __init__(self, name = 'Главный'):
        super().__init__(name = name)
        box1 = BoxLayout()
        box2 = BoxLayout()
        box3 = BoxLayout()
        box4 = BoxLayout()
        boxv = BoxLayout(orientation = 'vertical')
        boxv2 = BoxLayout(orientation = 'vertical', padding = 8)

        txt = Label(text = "Выбери Экран" )
        btn1 = Button(text = 'Экран 1')
        btn2 = Button(text = 'Экран 2')
        btn3 = Button(text = 'Экран 3')
        btn4 = Button(text = 'Экран 4')
        box1.add_widget(btn1)
        box2.add_widget(btn2)
        box3.add_widget(btn3)
        box4.add_widget(btn4)
        boxv.add_widget(txt)
        boxv2.add_widget(box1)
        boxv2.add_widget(box2)
        boxv2.add_widget(box3)
        boxv2.add_widget(box4)
        btn1.on_press = self.next1
        btn2.on_press = self.next2
        btn3.on_press = self.next3
        btn4.on_press = self.next4


    def next1(self):
        self.manager.transiction.direction = 'left'
        self.manager.current = '1'
    def next2(self):
        self.manager.transiction.direction = 'up'
        self.manager.current = '2'
    def next3(self):
        self.manager.transiction.direction = 'right'
        self.manager.current = '3'
    def next4(self):
        self.manager.transiction.direction = 'down'
        self.manager.current = '4'
class FirstScr(Screen):
    def __init(self,name = 'Экран 1'):
        super().__init__(name = name)
        btn1 = Button('Вернуться на главный')
        Layout1 = Layout()
        Layout1.add_widget(btn1)
        btn1.on_press = self.next
    def next(self):
        self.manager.transiction.direction = 'right'
        self.manager.current = 'Главный'
class SecondScr(Screen):
    def __init(self,name = 'Экран 2'):
        super().__init__(name = name)
        btn1 = Button('Вернуться на главный')
        Layout1 = Layout()
        Layout1.add_widget(btn1)
        btn1.on_press = self.next
    def next(self):
        self.manager.transiction.direction = 'down'
        self.manager.current = 'Главный'
class ThirdScr(Screen):
    def __init(self,name = 'Экран 3'):
        super().__init__(name = name)
        btn1 = Button('Вернуться на главный')
        Layout1 = Layout()
        Layout1.add_widget(btn1)
        btn1.on_press = self.next
    def next(self):
        self.manager.transiction.direction = 'left'
        self.manager.current = 'Главный'
class FourthScr(Screen):
    def __init(self,name = 'Экран 4'):
        super().__init__(name = name)
        btn1 = Button('Вернуться на главный')
        Layout1 = Layout()
        Layout1.add_widget(btn1)
        btn1.on_press = self.next
    def next(self):
        self.manager.transiction.direction = 'up'
        self.manager.current = 'Главный'
class MyApp(App):
    def build(self):
        sm = ScreenManager()
        sm.add_widget(MainScr())
        sm.add_widget(FirstScr())
        sm.add_widget(SecondScr())
        sm.add_widget(ThirdScr())
        sm.add_widget(FourthScr())
        return sm

MyApp().run()
