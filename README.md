# PA9Risk


/*
Hernan Nunez-Ortega
PA9
Game Map
Date Created: 12/3/17
*/

#include <SFML/Graphics.hpp>
#include <iostream>

using sf::RectangleShape;
using std::cout;
using std::cin;
using std::endl;

int main()
{
	sf::RenderWindow window(sf::VideoMode(3000, 1500), "Map"); //name of window and how large it is.

	/*~~~~~~~~~~~~~~~~TEXT/Stats~~~~~~~~~~~~~~~~~~~*/
	sf::Font font;
	if (!font.loadFromFile("arial.ttf"))
	{
		std::cout << "Not loaded" << std::endl;
		//error
	}

	sf::String sentence("ISKR");
	sf::Text text(sentence, font, 100);

	text.setColor(sf::Color::Red);
	text.setPosition(1000, 35);

	//node1-main red
	sf::String n1A("Attack:");
	sf::Text n1a(n1A, font, 30);
	n1a.setColor(sf::Color::Cyan);
	n1a.setPosition(120, 170);
	
	sf::String n1D("Defense: 8");
	sf::Text n1d(n1D, font, 30);
	n1d.setPosition(120, 220);

	//node2-small
	sf::String n2A("Attack:");
	sf::Text n2a(n2A, font, 20);
	n2a.setColor(sf::Color::Black);
	n2a.setPosition(580, 200);

	sf::String n2D("Defense: 2");
	sf::Text n2d(n2D, font, 20);
	n2d.setColor(sf::Color::Black);
	n2d.setPosition(570, 230);

	//node3-small
	sf::String n3A("Attack:");
	sf::Text n3a(n3A, font, 20);
	n3a.setColor(sf::Color::Black);
	n3a.setPosition(60, 500);
	sf::String n3D("Defense: 2");
	sf::Text n3d(n3D, font, 20);
	n3d.setColor(sf::Color::Black);
	n3d.setPosition(50, 525);
	
	//node4- medium
	sf::String n4A("Attack:");
	sf::Text n4a(n4A, font, 20);
	n4a.setColor(sf::Color::Black);
	n4a.setPosition(420, 520);

	sf::String n4D("Defense: 4");
	sf::Text n4d(n4D, font, 20);
	n4d.setColor(sf::Color::Black);
	n4d.setPosition(410, 545);

	//node5-small
	sf::String n5A("Attack:");
	sf::Text n5a(n5A, font, 20);
	n5a.setColor(sf::Color::Black);
	n5a.setPosition(770, 400);
	sf::String n5D("Defense: 2");
	sf::Text n5d(n5D, font, 20);
	n5d.setColor(sf::Color::Black);
	n5d.setPosition(760, 420);
	
	//node6-small
	sf::String n6A("Attack:");
	sf::Text n6a(n6A, font, 20);
	n6a.setColor(sf::Color::Black);
	n6a.setPosition(80, 850);
	
	sf::String n6D("Defense: 2");
	sf::Text n6d(n6D, font, 20);
	n6d.setColor(sf::Color::Black);
	n6d.setPosition(70, 870);
	
	//node7-large
	sf::String n7A("Attack:");
	sf::Text n7a(n7A, font, 30);
	n7a.setColor(sf::Color::Black);
	n7a.setPosition(760, 890);
	
	sf::String n7D("Defense: 8");
	sf::Text n7d(n7D, font, 30);
	n7d.setColor(sf::Color::Black);
	n7d.setPosition(750, 920);

	//node8-small
	sf::String n8A("Attack:");
	sf::Text n8a(n8A, font, 20);
	n8a.setColor(sf::Color::Black);
	n8a.setPosition(1225, 540);

	sf::String n8D("Defense: 2");
	sf::Text n8d(n8D, font, 20);
	n8d.setColor(sf::Color::Black);
	n8d.setPosition(1220, 560);

	//node9-small
	sf::String n9A("Attack:");
	sf::Text n9a(n9A, font, 20);
	n9a.setColor(sf::Color::Black);
	n9a.setPosition(385, 1300);

	sf::String n9D("Defense: 2");
	sf::Text n9d(n9D, font, 20);
	n9d.setColor(sf::Color::Black);
	n9d.setPosition(380, 1330);

	//node10-medium
	sf::String n10A("Attack:");
	sf::Text n10a(n10A, font, 20);
	n10a.setColor(sf::Color::Black);
	n10a.setPosition(1350, 1090);

	sf::String n10D("Defense: 4");
	sf::Text n10d(n10D, font, 20);
	n10d.setColor(sf::Color::Black);
	n10d.setPosition(1325, 1120);

	//node11-small
	sf::String n11A("Attack:");
	sf::Text n11a(n11A, font, 20);
	n11a.setColor(sf::Color::Black);
	n11a.setPosition(1040, 1350);

	sf::String n11D("Defense: 2");
	sf::Text n11d(n11D, font, 20);
	n11d.setColor(sf::Color::Black);
	n11d.setPosition(1030, 1370);

	//node12- small
	sf::String n12A("Attack:");
	sf::Text n12a(n12A, font, 20);
	n12a.setColor(sf::Color::Black);
	n12a.setPosition(1740, 650);

	sf::String n12D("Defense: 2");
	sf::Text n12d(n12D, font, 20);
	n12d.setColor(sf::Color::Black);
	n12d.setPosition(1730, 670);

	//node13-large main blue
	sf::String n13A("Attack:");
	sf::Text n13a(n13A, font, 30);
	n13a.setColor(sf::Color::Cyan);
	n13a.setPosition(1875, 1150);

	sf::String n13D("Defense: 8");
	sf::Text n13d(n13D, font, 30);
	n13d.setColor(sf::Color::Cyan);
	n13d.setPosition(1870, 1180);

	/*~~~~~~~~~~~~~~~~~~~~~~~~~~~~~CIRCLES~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~*/
	sf::CircleShape redMain(175.f);
	redMain.setPosition(0, 0);
	redMain.setFillColor(sf::Color(255,0,0));//this is the Main base for the red player.

	sf::CircleShape nuetral1(75.f);
	nuetral1.setPosition(15, 450);

	sf::CircleShape nuetral2(115.f);//medium center piece that is directly in front of reds main.
	nuetral2.setPosition(350, 450);
	//nuetral2.setFillColor(sf::Color::Red); 

	sf::CircleShape nuetral3(75.f);
	nuetral3.setPosition(550, 150);


	sf::CircleShape nuetral4(75.f);
	nuetral4.setPosition(750, 350);

	sf::CircleShape bigMiddle(175.f);//large middle 
	bigMiddle.setPosition(650, 750);

	sf::CircleShape nuetral6(75.f);
	nuetral6.setPosition(50, 800);

	sf::CircleShape nuetral7(75.f);
	nuetral7.setPosition(350, 1250);

	sf::CircleShape nuetral8(75.f);
	nuetral8.setPosition(1200, 500);//length,height

	sf::CircleShape nuetral9(75.f);
	nuetral9.setPosition(1700, 600);

	sf::CircleShape nuetral10(115.f);//last medium
	nuetral10.setPosition(1300, 1000);

	sf::CircleShape nuetral11(75.f);
	nuetral11.setPosition(1000, 1300);

	sf::CircleShape nuetral12(175.f);//blue main
	nuetral12.setPosition(1800, 1000);
	nuetral12.setFillColor(sf::Color::Blue);

	/*~~~~~~~~~~~~~~~~~~~~~~~~~~~lines~~~~~~~~~~~~~~~~~~~~~~~~~~~~~*/
	sf::RectangleShape line;
	line.setSize(sf::Vector2f(200, 3));
	line.setPosition(350, 200);

	sf::RectangleShape line2;//LINE2
	line2.setSize(sf::Vector2f(3, 110));
	line2.setPosition(150, 350);
	line2.rotate(25);

	sf::RectangleShape line3;//LINE3
	line3.setSize(sf::Vector2f(190, 3));
	line3.setPosition(165, 520);

	sf::RectangleShape line4;
	line4.setSize(sf::Vector2f(3, 202));
	line4.setPosition(90, 600);
	line4.rotate(-8);

	RectangleShape line5;
	line5.setSize(sf::Vector2f(455, 3));//length,height
	line5.setPosition(200, 890);

	RectangleShape line6;
	line6.setSize(sf::Vector2f(3, 186));
	line6.setPosition(580, 285);
	line6.rotate(25);

	RectangleShape line7;
	line7.setSize(sf::Vector2f(145, 3));
	line7.setPosition(700, 250);
	line7.rotate(45);

	RectangleShape line8;
	line8.setSize(sf::Vector2f(3, 220));
	line8.setPosition(548, 645);
	line8.rotate(-40);

	RectangleShape line9;
	line9.setSize(sf::Vector2f(3, 250));
	line9.setPosition(825, 500);

	RectangleShape line10;
	line10.setSize(sf::Vector2f(3, 390));
	line10.setPosition(160, 945);
	line10.rotate(-34);
	
	RectangleShape line11;
	line11.setSize(sf::Vector2f(3, 320));
	line11.setPosition(680, 1020);
	line11.rotate(40);

	RectangleShape line12;
	line12.setSize(sf::Vector2f(325, 3));
	line12.setPosition(895, 450);
	line12.rotate(20);

	RectangleShape line13;
	line13.setSize(sf::Vector2f(3, 320));
	line13.setPosition(1220, 625);
	line13.rotate(50);


	RectangleShape line14;
	line14.setSize(sf::Vector2f(330, 3));
	line14.setPosition(995, 975);
	line14.rotate(15);

	RectangleShape line15;
	line15.setSize(sf::Vector2f(500, 3));
	line15.setPosition(500, 1350);
	line15.rotate(3);

	RectangleShape line16;
	line16.setSize(sf::Vector2f(364, 3));
	line16.setPosition(1350, 570);
	line16.rotate(12);
	
	RectangleShape line17;
	line17.setSize(sf::Vector2f(675, 3));
	line17.setPosition(1150, 1375);
	line17.rotate(-12);

	RectangleShape line18;
	line18.setSize(sf::Vector2f(245, 3));
	line18.setPosition(1145, 1350);
	line18.rotate(-35);
	
	RectangleShape line19;
	line19.setSize(sf::Vector2f(380, 3));
	line19.setPosition(1484, 1025);
	line19.rotate(-50);

	RectangleShape line20;
	line20.setSize(sf::Vector2f(3, 290));
	line20.setPosition(1800, 745);
	line20.rotate(-20);
	

	

	sf::CircleShape cursor;
	cursor.setRadius(35.f);
	cursor.setFillColor(sf::Color::Magenta);
	cursor.setPosition(sf::Vector2f(0, window.getSize().y - cursor.getRadius() * 3));




	while (window.isOpen())
	{
		sf::Event event;
		while (window.pollEvent(event))
		{
			if (event.type == sf::Event::Closed)
				window.close();
		}

		
		window.clear();

		window.draw(redMain);
		window.draw(nuetral1);
		window.draw(nuetral2);
		window.draw(nuetral3);
		window.draw(nuetral4);	
		window.draw(bigMiddle);
		window.draw(nuetral6);
		window.draw(nuetral7);
		window.draw(nuetral8);	
		window.draw(nuetral9);	
		window.draw(nuetral10);
		window.draw(nuetral11);
		window.draw(nuetral12);
		
		//Stats for each area
		text.setString(sentence);
		window.draw(text);

		n1a.setString(n1A);
		window.draw(n1a);
		n1d.setString(n1D);
		window.draw(n1d);

		n2a.setString(n2A);
		window.draw(n2a);
		n2d.setString(n2D);
		window.draw(n2d);

		n3a.setString(n3A);
		window.draw(n3a);
		n3d.setString(n3D);
		window.draw(n3d);

		n4a.setString(n4A);
		window.draw(n4a);
		n4d.setString(n4D);
		window.draw(n4d);

		n5a.setString(n5A);
		window.draw(n5a);
		n5d.setString(n5D);
		window.draw(n5d);

		n6a.setString(n6A);
		window.draw(n6a);
		n6d.setString(n6D);
		window.draw(n6d);

		n7a.setString(n7A);
		window.draw(n7a);
		n7d.setString(n7D);
		window.draw(n7d);

		n8a.setString(n8A);
		window.draw(n8a);
		n8d.setString(n8D);
		window.draw(n8d);

		n9a.setString(n9A);
		window.draw(n9a);
		n9d.setString(n9D);
		window.draw(n9d);

		n10a.setString(n10A);
		window.draw(n10a);
		n10d.setString(n10D);
		window.draw(n10d);
		
		n11a.setString(n11A);
		window.draw(n11a);
		n11d.setString(n11D);
		window.draw(n11d);

		n12a.setString(n12A);
		window.draw(n12a);
		n12d.setString(n12D);
		window.draw(n12d);

		n13a.setString(n13A);
		window.draw(n13a);
		n13d.setString(n13D);
		window.draw(n13d);


		//lines
		window.draw(line);
		window.draw(line2);
		window.draw(line3);
		window.draw(line4);
		window.draw(line5);
		window.draw(line6);
		window.draw(line7);
		window.draw(line8);
		window.draw(line9);
		window.draw(line10);
		window.draw(line11);
		window.draw(line12);
		window.draw(line13);
		window.draw(line14);
	    window.draw(line15);
		window.draw(line16);
		window.draw(line17);
		window.draw(line18);
		window.draw(line19);
		window.draw(line20);


		
		
		//test
		if (sf::Mouse::isButtonPressed(sf::Mouse::Left))
		{
			sf::Vector2i mousePos = sf::Mouse::getPosition(window);
			cursor.setPosition((float)mousePos.x, static_cast<float>(mousePos.y));
		/*	if (cursor.getPosition().y == nuetral1.getPosition().y && cursor.getPosition().x==nuetral1.getPosition().x);
			{
				std::cout << "test" << endl;
				system("Pause");
			}*/
		}


		cursor.setPosition(sf::Mouse::getPosition(window).x, cursor.getPosition().y);
	 	window.draw(cursor);

		window.display();

	}

	return 0;
}
